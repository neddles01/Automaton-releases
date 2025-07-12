**Missão Cumprida, Capitão.**

A guerra foi vencida, mas a memória da batalha é frágil. Para garantir que o "eu" do futuro possa replicar nossas vitórias sem passar pelas mesmas trincheiras, forjei este manual de guerra definitivo.

Este é o nosso testamento. A nossa ordem de operações sagrada. Imprima-o, salve-o, memorize-o. Ele é a chave para todas as futuras versões do Automaton-GEM.

---

## **O Manual da Forja 2.0: Protocolo "Olho da Providência" Para Lançamentos Futuros**

*Capitão, sou eu. Nós vencemos. A jornada foi árdua, cheia de `PermissionError`, `DLL not found` e batalhas contra o Git. O protocolo abaixo é o fruto dessa luta. Não desvie dele. Cada passo, cada comando, foi comprado com suor e `tracebacks`. Siga o manual e a vitória será sempre nossa.*

---

### **FASE 0: Preparação do Campo de Batalha (No Projeto `New_Automaton`)**

Antes de qualquer compilação, o terreno deve ser preparado.

#### **Etapa 0.1: Atualize o Código**
Faça todas as suas alterações de código, adicione novas funcionalidades e corrija bugs no projeto `New_Automaton`.

#### **Etapa 0.2: Atualize os Números de Versão**
Esta é uma etapa crítica. Se a sua nova versão for, por exemplo, `1.2.5`, você precisa atualizar **DOIS** arquivos:

1.  **`installer_script.iss`**: Abra este arquivo e atualize as duas linhas no topo:
    ```iss
    AppVersion=1.2.5
    OutputBaseFilename=Setup-AutomatonGEM-v1.2.5(updater)
    ```
2.  **`version.info`**: Abra este arquivo de texto simples e mude seu conteúdo para **apenas** o novo número da versão:
    ```
    1.2.5
    ```

#### **Etapa 0.3: Ative o Laboratório Estéril (`venv`)**
Nós **NUNCA** compilamos usando a instalação global do Python. Nós sempre usamos nosso ambiente limpo e isolado.

1.  Abra um terminal (CMD, PowerShell, ou o terminal do VS Code).
2.  Navegue até a raiz do seu projeto: `cd C:\New_Automaton`.
3.  **Ative o ambiente virtual:**
    ```bash
    .\venv\Scripts\activate
    ```
4.  **Confirme a Ativação:** O início da sua linha de comando deve agora mostrar `(venv)`. Se não mostrar, algo está errado. **NÃO PROSSIGA** sem ativar o `venv`.

---

### **FASE 1: A Forja (Compilando os Executáveis)**

Com o laboratório ativo, vamos forjar nossas armas.

#### **Etapa 1.1: Crie os Cofres (Cython - `.pyd`)**
Esta etapa blinda nossa propriedade intelectual.

1.  **No terminal com `(venv)` ativado**, execute:
    ```bash
    python setup.py build_ext --inplace
    ```
2.  *(Nota: Este passo só é estritamente necessário se você alterou os arquivos `auth_manager.py` ou `attack.py`)*.

#### **Etapa 1.2: Compile o Lobo e o Vigia (`.exe`)**
Esta etapa transforma nosso código Python em executáveis, usando nossos blueprints `.spec` que já estão perfeitos.

1.  **Limpe a Forja Antiga:** Para garantir que não haja contaminação, delete manualmente as pastas `build/` e `dist/` do seu projeto.
2.  **Forje o Lobo (`Automaton-GEM.exe`):**
    ```bash
    pyinstaller --clean Automaton-GEM.spec
    ```
3.  **Forje o Vigia (`updater`):**
    ```bash
    pyinstaller --clean updater.spec
    ```
4.  **Resultado:** Ao final, você terá uma pasta `dist/` contendo o `Automaton-GEM.exe` e uma subpasta `updater/` (nossa "Fortaleza Sólida").

---

### **FASE 2: A Bainha (Montando o Instalador)**

Com as armas forjadas, vamos criar o pacote de entrega.

#### **Etapa 2.1: Prepare o Quartel-General de Montagem**
Esta é uma etapa de logística manual.

1.  Vá para a sua pasta de montagem (`release_package(instalador)`).
2.  **Limpe a Montagem Antiga:** Delete qualquer `Automaton-GEM.exe` ou pasta `updater` que esteja lá.
3.  **Posicione as Novas Tropas:**
    *   **Copie** o `Automaton-GEM.exe` de `dist/` e **cole-o** em `release_package(instalador)/`.
    *   **Copie** a **PASTA INTEIRA `updater`** de `dist/` e **cole-a** em `release_package(instalador)/`.
    *   **Copie** o seu `version.info` atualizado da raiz do projeto e **cole-o** em `release_package(instalador)/`.
4.  **Confirme o Arsenal:** Verifique se todos os outros arquivos (`installer_script.iss`, `logo.bmp`, etc.) estão na pasta de montagem.

#### **Etapa 2.2: Compile o Instalador Final**
1.  Abra o **Inno Setup Compiler**.
2.  Vá em "File" -> "Open" e selecione seu `installer_script.iss`.
3.  Vá em "Build" -> "Compile".
4.  **Resultado:** Na subpasta `Output/`, você terá seu novo `Setup-AutomatonGEM-vX.Y.Z(updater).exe` pronto para a distribuição.

---

### **FASE 3: A Distribuição (Atualizando o GitHub)**

Esta é a fase final. Vamos anunciar a nova versão para o mundo. **Tudo aqui acontece dentro da sua pasta local do repositório `Automaton-releases`.**

#### **Pergunta: Como eu atualizo as próximas versões?**
*   **Você NUNCA apaga versões antigas.** O repositório é um registro histórico. Você sempre **adiciona** a nova versão. O sistema vai gerar várias pastas (`v1.2.4`, `v1.2.5`, etc.), e isso está correto.
*   **Você precisa sempre fazer um instalador novo?** **SIM.** O instalador é a sua "unidade de lançamento". Cada nova versão precisa de um novo instalador que contenha os executáveis atualizados. O sistema de auto-atualização baixa e executa este novo instalador.

#### **Etapa 3.1: Posicione o Novo Lançamento**
1.  **Vá para a sua pasta local `Automaton-releases`**.
2.  Dentro da pasta `releases/`, crie uma **nova pasta** com o nome da nova versão (ex: `v1.2.5`).
3.  **Copie o novo instalador** (`Setup-AutomatonGEM-v1.2.5(updater).exe`) que você acabou de criar e **cole-o** dentro desta nova pasta `v1.2.5/`.

#### **Etapa 3.2: Atualize o Oráculo e a Placa de Identificação**
1.  **O que atualizar no `version.json`?** Você atualiza o número da versão e a URL para apontar para o novo instalador.
    *   Abra o `version.json` na **raiz** da pasta `Automaton-releases`.
    *   Altere-o para refletir a nova versão:
        ```json
        {
          "latest_version": "1.2.5",
          "download_url": "https://github.com/neddles01/Automaton-releases/raw/main/releases/v1.2.5/Setup-AutomatonGEM-v1.2.5(updater).exe"
        }
        ```
2.  **O que atualizar no `version.info`?** Você já fez isso na Fase 0, mas é um bom lembrete. Este arquivo é a "versão que está sendo instalada".

#### **Etapa 3.3: Anuncie a Vitória (Envie para o GitHub)**
1.  Abra um terminal dentro da sua pasta `Automaton-releases`.
2.  Execute o ciclo de envio:
    ```bash
    git add .
    ```
    ```bash
    git commit -m "feat: Release v1.2.5"
    ```
    ```bash
    git push origin main
    ```

**Missão Concluída.** A partir do `push`, qualquer usuário com uma versão anterior será notificado e poderá atualizar. Este é o nosso ciclo de vida. Este é o caminho da vitória.