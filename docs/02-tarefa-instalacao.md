# Etapa 2: Instalação Passo a Passo (Fase de Texto e Gráfica)

## 🎯 Objetivo
Interagir com o instalador em modo texto dentro do ambiente virtualizado do VirtualBox, gerenciar partições NTFS e conduzir a fase de configuração de interface gráfica.

---

## 📑 Roteiro de Execução

### Fase 1: Interface de Texto (Instalador Azul)
1.  Selecione a VM no VirtualBox e clique em **Iniciar** (Seta verde).
2.  Clique dentro da janela da tela preta que se abrirá. 
    > 💡 **Nota do VirtualBox:** Para liberar o ponteiro do mouse de dentro da tela do Windows XP nesta fase, pressione a tecla **CTRL Direita** (Host Key) do seu teclado físico.
3.  Assim que surgir a mensagem `Pressione qualquer tecla para iniciar a partir do CD...`, pressione `ESPAÇO`.
4.  Aguarde o carregamento dos arquivos. Na tela de boas-vindas, pressione `ENTER`.
5.  Pressione `F8` para aceitar o Contrato de Licença da Microsoft.
6.  Na tela de partições, selecione o `Espaço não particionado [20480 MB]`.
7.  Pressione `C` para criar partição, mantenha o tamanho total exibido e pressione `ENTER`.
8.  Selecione a partição `C: Partição 1` criada e pressione `ENTER`.
9.  Escolha a opção **Formatar a partição utilizando o sistema de arquivos NTFS** (Não utilize a opção rápida para simular um escaneamento real de trilhas do HD virtual).
10. Ao fim da cópia de arquivos, a máquina virtual reiniciará. **Não pressione nenhuma tecla no reboot**, permitindo que o sistema inicialize pelo HD virtual.

### Fase 2: Interface Gráfica do Windows XP
1.  Aguarde a abertura da janela do instalador gráfico do Windows.
2.  Na janela de opções regionais, clique em **Personalizar...**, mude o teclado para `Português (Brasil - ABNT2)` e clique em Avançar.
3.  Insira o seu nome completo no campo **Nome** e `LAB-VBOX` no campo **Organização**.
4.  Digite a chave de licença de 25 caracteres fornecida pelo professor.
5.  Defina o nome do computador como `VBOX-XP-SEUNOME` e avance sem definir senha de administrador.
6.  Confirme a data, hora e o fuso horário de Brasília.
7.  Nas configurações de rede, selecione **Configurações Normais**. No grupo de trabalho, mantenha `WORKGROUP`.
8.  Aguarde a finalização dos processos e o terceiro reinício da VM.

---

## 📝 Entregáveis desta Etapa

### 📸 [EVIDÊNCIA]
<img width="1919" height="1079" alt="Captura de tela 2026-05-22 111935" src="https://github.com/user-attachments/assets/98e08c4a-4b3a-4e66-ba0b-ade11c5bebbe" />


### ❓ [QUESTÃO 2]
Se por engano você pressionasse uma tecla quando a VM reiniciou entre a Fase 1 e a Fase 2, o que aconteceria com o fluxo da atividade? O instalador continuaria de onde parou ou reiniciaria o processo do zero?

**Sua Resposta:**
> Se você pressionar uma tecla quando a máquina virtual reiniciar entre a Fase 1 (Modo Texto) e a Fase 2 (Interface Gráfica), o processo de instalação reiniciará do zero.
> Por que isso acontece?
Durante a reinicialização, o VirtualBox lê a ordem de boot configurada. Como a imagem ISO do Windows XP ainda está "inserida" no leitor de CD virtual, a máquina exibirá a clássica mensagem na tela preta:

"Pressione qualquer tecla para iniciar a partir do CD..."

Se você pressionar uma tecla: A VM vai ignorar o disco rígido (onde os arquivos temporários da Fase 1 foram copiados) e carregará novamente o instalador direto do CD, voltando para a tela azul de formatação e cópia de arquivos.

O que fazer se isso acontecer: Você perderá o progresso e terá que repetir a Fase 1. Para corrigir, basta reiniciar a VM novamente e, desta vez, não tocar em nenhuma tecla, deixando o contador de tempo expirar.

O sistema entenderá que deve passar para o próximo dispositivo da ordem de boot: o disco rígido virtual (VDI), onde a Fase 2 (exatamente aquela tela dos 39 minutos) continuará normalmente.

---
[⬅️ Voltar para a Etapa 1](01-tarefa-pre-requisitos.md) | [Ir para a Etapa 3 ➡️](03-tarefa-pos-instalacao.md)
