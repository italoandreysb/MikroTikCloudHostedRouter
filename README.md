# Mikrotik Virtual Cloud Hosted Router

O Mikrotik é composto por **7** níveis de licença. São elas:

- Licença Trial Mode
- Free Demo
- Level 03 (WISP CPE)
- Level 4 (WISP)
- Level 5 (WISP)
- Level 6 (Controller)
- **CHR (Clouded Hosted Router)**

### Licença CHR (Clouded Hosted Router)
A Licença CHR é uma versão do RouterOs executada em uma máquina virtual (VM). Ela suporta as arquiteturas x86 de 64 bits e pode ser utilizada na maioria das VM’s — como VMWare, Hyper-V, VirtualBox, KVM e outros. Possui todos os recursos do RouterOS por padrão, porém o modelo de licenciamento é diferente das outras versões.

### Requisitos mínimos para a licença CHR
Versão do pacote: RouterOS v6.34 ou mais recente
CPU do host: 64 bits com suporte a virtualização
RAM: 128 MB ou mais
Disco: 128 MB de espaço em disco para o disco rígido virtual CHR (máximo: 16 GB)

### O licenciamento CHR possui 5 níveis de licença:

- Livre: Permite que seja utilizada de maneira indefinida,  com limite de  1 Mbps de Upload  por interface, todos os demais recursos são disponíveis sem restrições
- Avaliação de 60 Dias: Possui a instalação de forma gratuita, podendo testar o aumento das licenças P1/ P10 / PU com 60 tentativas.
- P1 Perpétua-1:Permite que seja utilizada de maneira indefinida, com limite de  1 Gbps de Upload  por interface, todos os demais recursos são disponíveis sem restrições É possível fazer upgrade de p1 para p10 ou p-ilimitado Após a compra da atualização, a licença anterior ficará disponível para uso posterior em sua conta.
- P10 Perpétua-10: Permite que seja utilizada de maneira indefinida, com limite de  10 Gbps de Upload  por interface, todos os demais recursos são disponíveis sem restrições É possível fazer upgrade de p10 para p-ilimitado Após a compra da atualização, a licença anterior ficará disponível para uso posterior em sua conta.
- P-Ilimitado: Permite que seja utilizada de maneira indefinida, é uma licença de alto nível e não possuí limitações pré-definidas.

## Procedimento:

1. Copiando o link da imagem da Mikrotik:

Acesse o [site da Mikrotik](https://mikrotik.com/download), na sessão de "Cloud Hosted Router" copie o endereço de link da versão "long term" de "Raw Disk image". 
	
Será algo assim: https://download.mikrotik.com/routeros/6.48.6/chr-6.48.6.img.zip

2. Acessando o Proxmox via terminal, baixe e extraia a imagem com o unzip:

```
  $ wget https://download.mikrotik.com/routeros/6.48.6/chr-6.48.6.img.zip
  $ apt update
  $ apt install unzip
  $ unzip chr-6.48.6.img.zip
```

4. Crie uma VM no proxmox via Interface gráfica.

5. Com a VM já criada no Proxmox remova o disco:

- Clique em **"Hardware"**, selecione o disco, clique em **"detach"**.
- Selecione o "Disco não alocado" e clique em **"Remove"**

5. Importe a imagem para a VM:

```$ qm importdisk <id_VM> <arquivo_VMDK> <local_storage>```

Ex:

```$ qm importdisk 200 chr-6.46.2.vmdk local-lvm```

Neste momento o disco vai aparecer na VM como "Disco não usado 0", adicione-o selecionando a VM, clicando em **"Hardware"**, dê dois cliques em **"Unused Disk 0"** e em **"Adicionar"**

6. Inicie a VM.

7. Casoa a VM não inicie, verifique a ordem de boot em **"Options"**, **"Boot order"**. O disco deve estar habilitado e em primeiro.

8. Se tudo ocorreu bem, você deverá ver um pedido de usuário e senha, o padrão a Mikrotik é: Usuário "admin" e sem senha.

Fontes:
- [Wikipedia - MikroTik](https://wiki.mikrotik.com/wiki/Manual:CHR)
- [Vídeo - Install MikroTik CHR RouterOS on Proxmox Server](https://www.youtube.com/watch?v=wI98U1WBFFI)
- [Licenciamento - blog.wifire.me](https://blog.wifire.me/como-funciona-os-niveis-de-licenca-do-mikrotik/)
