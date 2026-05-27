# Etapa 4: Troubleshooting e Redes no VirtualBox

## 🎯 Objetivo
Solucionar travamentos comuns do VirtualBox ao lidar com sistemas legados e mitigar riscos de segurança através do isolamento de placas de rede virtuais.

---

## 📑 Roteiro de Execução

1.  **Troubleshooting de Integração (Se necessário):**
    *   Se o mouse travar ou sumir após a instalação, vá nas configurações da VM no VirtualBox, aba **Sistema** -> **Dispositivo de Apontamento** e mude de `Multi-touch Tablet` para `Mouse PS/2`.
2.  **Configuração de Rede Segura (Isolamento de Vulnerabilidades):**
    *   O Windows XP é vulnerável a ataques modernos de rede distribuída (como o exploit *EternalBlue* / *WannaCry*).
    *   Abra as configurações da VM no VirtualBox com ela desligada. Vá na aba **Rede**.
    *   No campo **Conectado a:** altere a opção padrão `NAT` para **Não Conectado** ou **Rede Interna (Internal Network)**.
    *   Isso garante que o sistema compartilhe arquivos com outras VMs do laboratório (se necessário), mas fique totalmente blindado e invisível contra varreduras e ataques vindos da Internet real.

---

## 📝 Entregáveis desta Etapa

### 📸 [EVIDÊNCIA]
<img width="794" height="490" alt="Captura de tela 2026-05-22 143044" src="https://github.com/user-attachments/assets/4005a47a-ebbb-468d-8e89-50949926fb7c" />


### ❓ [QUESTÃO 4]
Se mantivéssemos o adaptador de rede da máquina virtual do Windows XP configurado no modo "Placa em modo Bridge (Bridged Adapter)" conectada à rede Wi-Fi/cabeada pública da instituição, quais seriam as consequências imediatas em termos de segurança cibernética para o laboratório e para a VM?

**Sua Resposta:**
> Configurar uma máquina virtual (VM) com o Windows XP em modo Bridge (Bridged Adapter) diretamente conectada à rede pública de uma instituição é o equivalente digital a deixar a porta da frente de uma casa trancada apenas por um trinco enferrujado dos anos 2000.

No modo Bridge, a VM não fica protegida atrás do host; ela recebe um IP próprio da rede física, tornando-se um nó independente e visível para qualquer outro dispositivo conectado.

---
### 🏁 FIM DA ATIVIDADE
Com todas as seções preenchidas e imagens anexadas à pasta `/assets` do seu repositório local, execute os comandos do Git para registrar e subir sua atividade:

```bash
git add .
git commit -m "feat: conclusao do laboratorio de instalacao do winxp no virtualbox"
git push origin main
