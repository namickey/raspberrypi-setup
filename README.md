# raspberrypi-setup

## �{�� + �A���t�@

* Raspberry Pi4 8GB
* SSD + SATA6��USB�ϊ��P�[�u���@��SD�J�[�h�͎g�p���Ȃ�
* USB typeC �d���^�b�v
* microHDMI��HDMI�P�[�u���@�����ڑ��삷�邽��
* �f�B�X�v���C�@�����ڑ��삷�邽��
* �L�[�{�[�h�@�����ڑ��삷�邽��
* �}�E�X�@�����ڑ��삷�邽��
* �m�[�gPC�@��VNC�N���C�A���g��

## �C���X�g�[��

�ȉ��A�c�[�����g����Raspberry Pi OS(32-bit)���C���X�g�[������  
SD�J�[�h�ł͂Ȃ��āASSD�ɂ��C���X�g�[���\  

Raspberry Pi Imager  
https://www.raspberrypi.com/software/  

�����OS�N����ɂ́A���[�U�ƃp�X���[�h�A���P�[�V�����A����LAN�̐ݒ�Ȃǂ��s���B  


## �{�� + �����P�[�X = ����LAN�̕s��

�S�̂𕢂��`�̋����P�[�X������ƁA����LAN���ڑ��ł��Ȃ��Ȃ����B  
��p���@�ɂ��Ă͌ʂɏ����ȃq�[�g�V���N���g�p����B  


## �p�ꉻ

�f�B���N�g�������p��֕ύX����
```bash
LC_ALL=C xdg-user-dirs-update --force
```

## ���{�����

���{�����
```bash
sudo apt install fcitx-mozc
```
## ntp

Raspberry Pi NTP�T�[�o�[�Ƃ̎�������
https://tarufu.info/raspberry-pi-ntp/

## ssh

���J������
```
ssh-keygen -t rsa -b 4096
```

SSH�̗L����  
https://qiita.com/c60evaporator/items/ebe9c6e8a445fed859dc#ssh%E3%82%92%E5%85%AC%E9%96%8B%E9%8D%B5%E8%AA%8D%E8%A8%BC%E3%81%AB%E5%A4%89%E6%9B%B4  

SSH�����J���F�؂ɕύX  
https://qiita.com/c60evaporator/items/ebe9c6e8a445fed859dc#ssh%E3%82%92%E5%85%AC%E9%96%8B%E9%8D%B5%E8%AA%8D%E8%A8%BC%E3%81%AB%E5%A4%89%E6%9B%B4  

�e��SSH�ݒ�̕ύX  
https://qiita.com/c60evaporator/items/ebe9c6e8a445fed859dc#%E5%90%84%E7%A8%AEssh%E8%A8%AD%E5%AE%9A%E3%81%AE%E5%A4%89%E6%9B%B4  


## VNC

VNC��Raspberry Pi�Ƀ����[�g�f�X�N�g�b�v�ڑ� (Windows/Mac/Linux�Ή�)  
https://www.indoorcorgielec.com/resources/raspberry-pi/raspberry-pi-vnc/  

�w�b�h���X�𑜓x�̐ݒ�  
https://invisiblepotato.com/raspberrypi05/  

## ssh�g���l�� + VNC-Client

�ȉ��R�}���h�ō쐬����SSH�g���l�����g���āAlocalhost:5901�Ɍ�����VNC�ڑ�����B

```bash
ssh -L 5901:localhost:5900 <userid>@<ipaddress> -N
```

## firewall

SSH���g�p���邽��22�ԃ|�[�g�������J����B  
VNC��5900�|�[�g�͎g�p���Ȃ��̂ŊJ���Ȃ��BSSH�g���l�����g����VNC���s���B  

```bash
sudo apt install gufw
```

