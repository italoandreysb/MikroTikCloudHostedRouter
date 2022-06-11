
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
