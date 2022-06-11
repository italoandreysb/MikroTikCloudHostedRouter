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
- Versão do pacote: RouterOS v6.34 ou mais recente
- CPU do host: 64 bits com suporte a virtualização
- RAM: 128 MB ou mais
- Disco: 128 MB de espaço em disco para o disco rígido virtual CHR (máximo: 16 GB)

### O licenciamento CHR possui 5 níveis de licença:

- Livre: Permite que seja utilizada de maneira indefinida,  com limite de  1 Mbps de Upload  por interface, todos os demais recursos são disponíveis sem restrições
- Avaliação de 60 Dias: Possui a instalação de forma gratuita, podendo testar o aumento das licenças P1/ P10 / PU com 60 tentativas.
- P1 Perpétua-1:Permite que seja utilizada de maneira indefinida, com limite de  1 Gbps de Upload  por interface, todos os demais recursos são disponíveis sem restrições É possível fazer upgrade de p1 para p10 ou p-ilimitado Após a compra da atualização, a licença anterior ficará disponível para uso posterior em sua conta.
- P10 Perpétua-10: Permite que seja utilizada de maneira indefinida, com limite de  10 Gbps de Upload  por interface, todos os demais recursos são disponíveis sem restrições É possível fazer upgrade de p10 para p-ilimitado Após a compra da atualização, a licença anterior ficará disponível para uso posterior em sua conta.
- P-Ilimitado: Permite que seja utilizada de maneira indefinida, é uma licença de alto nível e não possuí limitações pré-definidas.

### Como checar o nível licença:

Acesse o terminal do mikrotik e digite:

  ```system licence print```

## Procedimento de instalação da CRS:

- Lique [AQUI](InstalandoCHR.md) para ver como executar o processo.
