# Leitor de Crachás & RFID - Prumo Engenharia (Versão Web)

Aplicativo web local moderno e ágil para associação de crachás:
1. **Leitura de QR Code (Matrícula)** via câmera web nativa (`html5-qrcode`).
2. **Consulta instantânea do Nome** na planilha `Relatorio Motoristas.XLS`.
3. **Leitura do Código RFID** via leitor USB (J-M15) usando a Web Serial API.
4. **Finalização com Barra de Espaço** ou botão Confirmar.
5. **Cópia direta para o Excel** (Ctrl+C / Ctrl+V) formatado em linhas e colunas.

---

## 🚀 Como Iniciar

Dê dois cliques em:
👉 **`iniciar_leitor.bat`** (ou abra diretamente o arquivo **`index.html`** no Google Chrome / Microsoft Edge).

A página é **100% autônoma (HTML/JS nativo)**, sem necessidade de backend Python rodando. Tudo roda direto no seu navegador com máximo desempenho e baixa latência.

---

## 📋 Como Usar

1. **Câmera:** Ao abrir a página no navegador, permita o acesso à câmera. O feed de vídeo será exibido ao vivo com a área de escaneamento.
2. **Leitor RFID USB:** Clique no botão azul **"🔌 Conectar Leitor USB"** e selecione a porta serial do leitor (geralmente `Dispositivo Serial USB / COM3`).
3. **Ajustes de Imagem da Câmera (Sem Mudar Resolução):**
   * **⚙️ Ajustes de Imagem:** Permite ajustar **Brilho**, **Contraste**, **Nitidez** e **Saturação** em controles idênticos aos das Configurações de Câmera do Windows 11.
   * **⚡ Melhor Leitura:** Aplica em 1 clique o preset ideal para leitura de QR Codes (contraste elevado, nitidez e saturação equilibrada) sem alterar a resolução do sensor.
   * **🔄 Redefinir configurações:** Funciona exatamente como o botão *"Redefinir configurações padrão da câmera"* do Windows, retornando brilho, contraste, nitidez e saturação aos padrões de fábrica e liberando o hardware para reuniões no Teams/Meet.
   * **🖥️ Câmeras do Windows:** Atalho que abre diretamente a tela nativa de configurações de câmera do Windows.
4. **Leitura e Associação (Fluxo 100% Automático):**
   * Aproxime o **QR Code do crachá** na câmera: a matrícula e o nome do colaborador são preenchidos automaticamente.
   * Aproxime o **cartão no leitor RFID**: o código numérico é capturado.
   * **Confirmação Automática:** Com a opção **⚡ Auto-confirmar** ativa (ligada por padrão), assim que o QR e o RFID são lidos, o cartão é confirmado e gravado no topo da lista automaticamente, já limpando os campos e ficando pronto para o próximo crachá!
   * Caso desmarque o Auto-confirmar, você pode confirmar manualmente pressionando a **Barra de Espaço** (ou clicando no botão verde).
4. **Proteção Contra Duplicidades:** Se um cartão RFID ou Matrícula já registrado for lido novamente, o sistema emite um bipe sonoro de erro, trava a gravação automática e exibe uma janela de alerta com os dados do cadastro anterior (Nome, Matrícula, RFID e Horário). O operador deve clicar em **OK** (ou apertar `Enter`/`Espaço`) para descartar a leitura repetida e ler o crachá correto.
5. **Lista de Apoio (Informações Vinculadas / Responsável):** Clique no botão **"📋 Lista de Apoio"** no topo para colar duas colunas copiadas do Excel (Coluna 1: Matrícula, Coluna 2: Responsável ou qualquer observação). Ao ler o QR Code de um crachá dessa lista, a informação aparece destacada em roxo na tela em tempo real, facilitando a separação física dos crachás.
6. **Copiar para o Excel:**
   * Clique em **"📋 Copiar para o Excel (Ctrl+C)"** (ou pressione `Ctrl+C`).
   * No Excel, clique na célula desejada e pressione `Ctrl + V`.
   * Ordem das colunas: **Código Cartão (RFID)** | **Matrícula (sem zero à esquerda)** | **Nome do Motorista**.

---

## ⌨️ Atalhos de Teclado

| Tecla | Ação |
| :--- | :--- |
| **Barra de Espaço** | Confirma o cartão e insere no topo da lista |
| **Ctrl + C** | Copia todos os cartões para colar no Excel |
| **F2** | Limpa os dados de QR Code para reler |
| **F3** | Limpa os dados de RFID para reler |
| **Esc** | Limpa os campos da leitura atual / fecha modais |
