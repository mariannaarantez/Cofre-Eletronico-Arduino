#  Cofre Eletrônico com Senha Analógica (Arduino)

> Protótipo de um sistema de segurança controlado por Arduino, onde o desbloqueio é feito através de uma "senha analógica" definida por dois potenciômetros.

## 📜 Sobre o Projeto

Este é um projeto acadêmico desenvolvido para a disciplina de Automação, que demonstra na prática os conceitos de controle de acesso, leitura de sensores e acionamento de atuadores.

A ideia central é um cofre eletrônico que substitui uma senha digital convencional por uma **combinação analógica secreta**. O usuário precisa ajustar dois potenciômetros em posições muito específicas para liberar a trava. Um display LCD fornece feedback visual em tempo real, informando se o cofre está trancado ou se o acesso foi liberado, tornando a interação mais clara e intuitiva.

## ✨ Funcionalidades

* **Senha Analógica:** Um método de autenticação criativo baseado na leitura de valores analógicos.
* **Feedback Visual:** Um display LCD 16x2 informa o status atual do sistema ("Cofre Trancado" / "Acesso Liberado").
* **Controle de Atuador:** Acionamento de uma fechadura solenoide de 12V através de um módulo relé, garantindo o isolamento entre os circuitos de controle e de potência.

## 🛠️ Hardware Utilizado

* Arduino UNO (ou similar)
* 2x Potenciômetros (10kΩ)
* Display LCD 16x2 (preferencialmente com módulo I2C para facilitar a conexão)
* Módulo Relé 1 Canal 5V
* Fechadura Solenoide 12V
* Protoboard e Jumpers para as conexões
* Fonte de alimentação externa de 12V para a fechadura

## ⚙️ Como Funciona

1.  Ao ser ligado, o sistema inicia com o cofre trancado, e o LCD exibe a mensagem "Cofre Trancado".
2.  O usuário gira os dois potenciômetros até encontrar a combinação secreta pré-definida no código.
3.  O Arduino lê continuamente os valores. Se a combinação estiver correta (dentro de uma pequena margem de tolerância), ele executa duas ações:
    * Envia um sinal para o módulo relé, que ativa a fechadura solenoide e destrava o cofre.
    * Atualiza a mensagem no LCD para "Acesso Liberado".
4.  Após alguns segundos (ou ao girar os potenciômetros para fora da combinação), o sistema se tranca novamente.

## 🚀 Como Usar

1.  Clone este repositório.
2.  Monte o circuito conforme o esquemático (se você tiver uma imagem do circuito, pode colocar aqui).
3.  Abra o arquivo `.ino` na IDE do Arduino.
4.  Faça o upload do código para a sua placa Arduino.
5.  Pronto! O sistema estará operacional.
