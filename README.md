# Renomeador de Arquivos Pro 📁✨

Bem-vindo ao Renomeador de Arquivos Pro! Esta é uma aplicação de desktop desenvolvida em Python com Tkinter/TTK, projetada para ajudá-lo a renomear arquivos em lote de forma eficiente e organizada. Ideal para organizar fotos, documentos de projetos, materiais de marketing e muito mais!

## 🌟 Funcionalidades Principais

* **Renomeação em Lote:** Modifique os nomes de múltiplos arquivos de uma só vez.
* **Padrões de Nomenclatura Flexíveis:** Defina um padrão usando campos como:
    * `TIPO DOC`: Sugerido automaticamente pela extensão do arquivo, mas editável.
    * `Descrição`: Utilize o nome original do arquivo como base se deixado em branco, ou defina uma descrição personalizada.
    * `Cliente`: Adicione um identificador de cliente (sugerido em CAIXA ALTA).
    * `Data`: Insira uma data no formato `AAAAMMDD` ou `N` para não incluir.
    * `Versão`: Adicione informações de versionamento (ex: `v1`, `vFinal`).
* **Remoção de Texto:** Um modo dedicado para remover trechos de texto específicos dos nomes originais dos arquivos.
* **Pré-visualização Dinâmica:** Veja como os novos nomes ficarão *antes* de aplicar as alterações.
* **Tratamento Inteligente de Caracteres:** Acentos e caracteres especiais são automaticamente removidos ou substituídos para garantir nomes de arquivo válidos e limpos.
* **Gerenciamento de Duplicatas:**
    * Nomes propostos idênticos dentro de um mesmo lote de seleção são automaticamente numerados (ex: `ARQUIVO (1).ext`, `ARQUIVO (2).ext`).
    * Ao salvar no disco, se um nome de arquivo final já existir, um sufixo `_disco_(N)` é adicionado para evitar sobrescritas acidentais.
* **Pré-visualização de Imagens:** Selecione um único arquivo de imagem (JPG, PNG, GIF, etc.) para ver uma miniatura. (Requer a biblioteca Pillow).
* **Menu de Contexto:** Clique com o botão direito em um arquivo na lista para "Abrir arquivo" ou "Mostrar na pasta".
* **Atalhos de Teclado e Mouse:**
    * `Ctrl + A` (na lista de arquivos): Seleciona todos os arquivos.
    * `Enter` (nos campos do "Modo Padrão"): Confirma e aplica a renomeação para os arquivos selecionados.
    * `Enter` (no campo "Texto a remover"): Gera o nome proposto com o texto removido e pergunta se deseja renomear.
    * `Clique com o botão do meio do mouse` (nos campos do "Modo Padrão"): Limpa todos os campos de entrada desse modo.

## 🚀 Como Usar

### Pré-requisitos

1.  **Python 3.x** instalado no seu sistema.
2.  **Pillow (Opcional, para pré-visualização de imagens):** Se você deseja usar a funcionalidade de pré-visualização de imagens, instale a biblioteca Pillow:
    ```bash
    pip install Pillow
    ```

### Executando a Aplicação

1.  Clone ou baixe este repositório.
2.  Certifique-se de ter um arquivo de ícone chamado `app_icon.ico` na mesma pasta do script `renomeador_avançado.py` (ou o nome que você deu ao script principal) para que o ícone da janela seja carregado.
3.  Abra um terminal ou prompt de comando na pasta do projeto.
4.  Execute o script:
    ```bash
    python "renomeador avançado.py"
    ```
    (Substitua `"renomeador avançado.py"` pelo nome exato do seu arquivo, especialmente se ele contiver espaços).

### Passo a Passo da Interface

1.  **Selecionar Diretório:**
    * Clique no botão **"Selecionar Diretório"** no canto superior esquerdo.
    * Navegue e escolha a pasta que contém os arquivos que você deseja renomear.
    * Os arquivos aparecerão na lista à esquerda, mostrando "Nome Original" e um "Nome Proposto" inicial (geralmente baseado no tipo de documento e no nome original).

2.  **Escolher o Modo de Operação:**
    * No painel direito, selecione o modo desejado:
        * **Padrão:** Para construir nomes usando campos estruturados.
        * **Remover Texto:** Para remover um trecho específico de texto dos nomes originais.

3.  **Modo "Renomear Padronizado":**
    * Preencha os campos na seção "Definir Padrão":
        * **TIPO DOC:** Será sugerido automaticamente pela extensão. Você pode apagar ou digitar um novo tipo.
        * **Descrição:** Se deixado em branco, o nome original do arquivo (sem extensão e sanitizado) será usado. Caso contrário, digite a descrição desejada.
        * **Cliente:** Opcional.
        * **Data:** Digite no formato `AAAAMMDD` (ex: `20240529`) ou `N` para não incluir a data. Um status ao lado indicará se o formato é válido.
        * **Versão:** Opcional (ex: `v1`, `final`).
    * **Selecionar Arquivos:** Clique nos arquivos na lista para selecioná-los. Use `Ctrl + A` para selecionar todos.
    * **Pré-visualização:** Conforme você digita nos campos e seleciona arquivos, a coluna "Nome Proposto" para os itens selecionados será atualizada dinamicamente.
    * **Pré-visualização de Imagem:** Se um único arquivo de imagem for selecionado, uma miniatura aparecerá no canto inferior direito.

4.  **Modo "Remover Texto do Nome":**
    * **Selecionar Arquivos:** Clique nos arquivos na lista dos quais você deseja remover texto.
    * **Digitar Texto:** No campo "Texto a remover do Nome Original:", digite o trecho exato que você quer que seja removido.
    * **Pré-visualização:** A coluna "Nome Proposto" para os arquivos selecionados será atualizada, mostrando como o nome original ficaria sem o texto especificado.
    * **Aplicar Remoção ao Proposto:** Clique no botão **"Remover Texto (Gerar Proposto)"**. Isso confirma a remoção para os nomes propostos dos arquivos selecionados.
        * Pressionar `Enter` neste campo também tem o mesmo efeito e, em seguida, perguntará se deseja prosseguir para a renomeação final.

5.  **Menu de Contexto (Lista de Arquivos):**
    * Clique com o botão direito em um arquivo na lista para:
        * **Abrir arquivo:** Tenta abrir o arquivo selecionado com o programa padrão.
        * **Mostrar na pasta:** Abre a pasta onde o arquivo está localizado no seu explorador de arquivos.

6.  **Renomear os Arquivos:**
    * Após definir os nomes propostos (seja pelo Modo Padrão ou Modo Remoção):
    * Clique no botão azul **"Renomear Selecionados"** (ou "Renomear Itens com Nome Proposto", dependendo da versão do texto do botão) na parte inferior do painel de opções.
    * Uma caixa de diálogo aparecerá pedindo confirmação para o lote de arquivos.
    * Se você confirmar, os arquivos selecionados serão renomeados no disco.
    * **Atalho:** No "Modo Padrão", pressionar `Enter` em qualquer um dos campos de entrada também acionará esta etapa de confirmação e renomeação para os arquivos selecionados.

7.  **Atalhos Adicionais:**
    * **Limpar Campos (Modo Padrão):** Clique com o botão do meio do mouse (botão do scroll) sobre qualquer um dos campos de entrada do "Modo Padrão" (ou no botão "Limpar Campos Padrão") para limpar todos eles e redefinir os placeholders.

## 🛠️ Para Desenvolvedores (Compilando para .exe com PyInstaller)

Se você deseja criar um arquivo executável (`.exe`) para distribuir sua aplicação, pode usar o PyInstaller. Após instalá-lo (`pip install pyinstaller`), navegue até a pasta do seu script no terminal e execute:

```bash
pyinstaller --onefile --windowed --icon="app_icon.ico" "seu_script.py"
