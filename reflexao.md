# Reflexão sobre a atividade

A atividade foi realizada individualmente, usando dois ambientes locais, A e B, para simular o trabalho em um repositório compartilhado.

As duas cópias partiram da mesma versão do README.md. No ambiente A, o título foi alterado para “Projeto Git de Laura Ferreira”. No ambiente B, foi alterado para “Prática de colaboração com Git”. As alterações foram registradas em commits separados.

Depois que o ambiente A enviou seu commit, o envio do ambiente B foi recusado porque o remoto já tinha uma alteração que ainda não existia naquela cópia. O comando git pull --no-rebase trouxe essa alteração e gerou um conflito, pois os dois commits modificavam a mesma linha.

A resolução consistiu em escolher um título que reunisse as duas propostas, apagar os marcadores de conflito, executar git add README.md e criar o commit “Resolve conflito no título do README”. Em seguida, a versão resolvida foi enviada ao remoto, e o ambiente A foi atualizado com git pull.

O exercício demonstra que git push envia commits, git pull traz e integra alterações, e git clone cria uma cópia do repositório com seu histórico. Quando há mudanças concorrentes na mesma linha, o Git precisa de uma decisão sobre qual conteúdo manter. Consultar o estado do projeto e sincronizar as cópias ajuda a identificar essas situações.

A simulação usou um repositório remoto local para executar os comandos de envio e atualização. O histórico resultante foi publicado no GitHub pela integração disponível. Não houve participação de uma segunda pessoa.

Os registros da execução e o conteúdo que apresentou conflito estão em evidencia-conflito.md.
