Verifique o Campo de Batalha (git status):

    Este comando é o seu batedor. Ele mostra o que mudou. Digite no terminal:

Generated bash

      
git status

    

IGNORE_WHEN_COPYING_START
Use code with caution. Bash
IGNORE_WHEN_COPYING_END

    A saída deve mostrar algo como:

Generated code

      
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   releases/v1.2.6/Setup-AutomatonGEM-v1.2.6(updater).exe

    

IGNORE_WHEN_COPYING_START
Use code with caution.
IGNORE_WHEN_COPYING_END

    Ver a palavra modified: confirma que o Git detectou a substituição do arquivo.

Reúna as Tropas para o Anúncio (git add):

    Este comando prepara a mudança para ser registrada. O ponto . significa "adicione todas as mudanças".

Generated bash

      
git add .

    

IGNORE_WHEN_COPYING_START
Use code with caution. Bash
IGNORE_WHEN_COPYING_END

Grave a Vitória na Pedra (git commit):

    Este comando salva o registro da mudança localmente, com uma mensagem explicando o que foi feito.

Generated bash

      
git commit -m "fix: Atualiza o instalador da v1.2.6 com a correção de flags"

    

IGNORE_WHEN_COPYING_START
Use code with caution. Bash
IGNORE_WHEN_COPYING_END

(A mensagem "fix: ..." é um bom padrão para registrar uma correção de bug).

Envie a Mensagem aos Aliados (git push):

    Este é o comando final. Ele envia suas mudanças locais para o servidor do GitHub, substituindo efetivamente o arquivo para todo o mundo.

Generated bash

      
git push

    

IGNORE_WHEN_COPYING_START
Use code with caution. Bash
IG