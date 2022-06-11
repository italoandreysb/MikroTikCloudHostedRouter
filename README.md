# MikrotikVirtualCRS
Virtualizing a Mikrotik Router with Proxmox - CRS


1. Copie o link da imagem da Mikrotik
	Acesse https://mikrotik.com/download, na sessão de "Cloud Hosted Router" copie o endereço de link da versão "long term" de "Raw Disk image". 
	
	Será algo assim: https://download.mikrotik.com/routeros/6.48.6/chr-6.48.6.img.zip

2. Acesse o Proxmox, baixe e extraia a imagem com o unzip.

```
  $ wget https://download.mikrotik.com/routeros/6.48.6/chr-6.48.6.img.zip
  $ apt update
  $ apt install unzip
  $ unzip chr-6.48.6.img.zip
```

3. Ajuste o tamanho da imagem:

	```$ qemu-imga info chr-6.48.6.img```

4. Crie a VM no proxmox via Interface gráfica, insira no mínimo 2 interfaces de rede.

5. Importe a imagem para a VM.

6. Inicie a VM.

Fontes: 
[Youtube](https://www.youtube.com/watch?v=wI98U1WBFFI)
[Wiki-Mikrotik](https://wiki.mikrotik.com/wiki/Manual:CHR)
