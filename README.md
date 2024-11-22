# Gerenciador de Bots - Home Hosting

## Descrição
Esta aplicação Python baseada no framework Flask permite criar, gerenciar e controlar bots de maneira simples e eficiente por meio de uma interface web. A aplicação possibilita a criação de bots, o upload e gerenciamento de seus arquivos, e o controle de execução dos processos de cada bot, como iniciar e parar.

## Funcionalidades
- **Interface web amigável** para gerenciar bots e seus arquivos.
- **Criação de bots** com atribuição de nomes únicos e pastas específicas.
- **Edição de bots** para atualizar o nome e o arquivo principal.
- **Upload e exclusão de arquivos** diretamente para a pasta de cada bot.
- **Execução e encerramento de bots** em terminais separados.
- **Armazenamento persistente** dos dados dos bots em um arquivo JSON.

## Estrutura do Script

### Imports Principais
- `Flask`: Para criar rotas e renderizar templates.
- `os` e `shutil`: Para manipulação de arquivos e diretórios.
- `json`: Para armazenamento e recuperação dos dados dos bots.
- `subprocess`: Para executar comandos no terminal.
- `psutil`: Para monitorar e encerrar processos do sistema.
- `platform`: Para verificar o sistema operacional.

### Configurações
- **Pasta de Upload**: `bots`, onde todos os arquivos dos bots são armazenados.
- **Arquivo JSON**: `bots.json`, utilizado para registrar informações persistentes de cada bot.

### Principais Funções
- **load_bots()**: Carrega a lista de bots do arquivo JSON.
- **save_bots(bots)**: Salva a lista de bots no arquivo JSON.
- **start_bot(bot_id)**: Inicia o processo de execução do bot no terminal.
- **stop_bot(bot_id)**: Finaliza o processo de execução do bot.
- **upload_file(bot_id)**: Faz o upload de arquivos para a pasta do bot correspondente.
- **delete_file(bot_id, filename)**: Exclui um arquivo específico da pasta do bot.
- **delete_bot(bot_id)**: Remove o bot do JSON e apaga sua pasta.

### Rotas da Aplicação
- `/`: Página inicial com a lista de bots.
- `/create`: Formulário para criar um novo bot.
- `/bot/<bot_id>`: Página detalhada para gerenciar um bot específico.
- `/upload/<bot_id>`: Endpoint para fazer upload de arquivos para o bot.
- `/delete/<bot_id>`: Endpoint para deletar um bot.
- `/start/<bot_id>`: Inicia o processo do bot.
- `/stop/<bot_id>`: Encerra o processo do bot.

## Execução
### Pré-requisitos
- **Python 3.7+**
- Instalar as dependências:
  ```bash
  pip install flask psutil
  ```

### Passos
1. Baixe a versão windows ou linux
  
2. Execute a aplicação:
   ```bash
   python app.py
   ```
3. Acesse a interface em: [http://127.0.0.1:5000](http://127.0.0.1:5000)

## Observações
- A aplicação foi projetada para sistemas Windows e Linux.

## Exemplo de Uso
1. **Criar Bot**:
   - Insira o nome do bot e clique em "Criar".
2. **Gerenciar Arquivos**:
   - Faça upload de arquivos necessários.
3. **Iniciar o Bot**:
   - Configure o arquivo principal e clique em "Iniciar".
4. **Monitorar Status**:
   - Veja o status (Ligado ou Desligado) diretamente na interface.

## Exemplo de Estrutura de Dados (`bots.json`)
```json
{
  "1": {
    "nome": "MeuBot",
    "main_file": "main.py",
    "status": "desligado",
    "pid": null,
    "terminal_title": "Terminal_MeuBot"
  }
}
```
Contribuições são bem-vindas!
