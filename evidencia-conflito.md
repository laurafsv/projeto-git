# Registro da prática

Simulação individual com dois ambientes e um remoto local.

## Conteúdo durante o conflito

```text
<<<<<<< HEAD
# Prática de colaboração com Git
=======
# Projeto Git de Laura Ferreira
>>>>>>> ede22d807acdd42759d64f653a08ddb77971719d

Atividade de Git e GitHub — LSPW.

Autora: Laura Ferreira (@laurafsv).

A prática foi realizada individualmente, com duas cópias locais (ambientes A e B) para simular alterações concorrentes no mesmo repositório.

O arquivo citacoes.html corresponde ao exemplo inicial da aula. A prática complementar registra um conflito no título deste README e sua resolução.
```

## Comandos e resultados

```text
$ git config user.name Laura Ferreira
$ git config user.email 205853177+laurafsv@users.noreply.github.com
$ git add README.md
$ git commit -m Adiciona README para a prática de colaboração
[main 5aa9f0e] Adiciona README para a prática de colaboração
 1 file changed, 9 insertions(+)
 create mode 100644 README.md
$ git clone --bare [pasta-da-pratica]/pratica-base [pasta-da-pratica]/pratica-remoto.git
Cloning into bare repository '[pasta-da-pratica]/pratica-remoto.git'...
done.
$ git clone [pasta-da-pratica]/pratica-remoto.git [pasta-da-pratica]/ambiente-a
Cloning into '[pasta-da-pratica]/ambiente-a'...
done.
$ git config user.name Laura Ferreira
$ git config user.email 205853177+laurafsv@users.noreply.github.com
$ git clone [pasta-da-pratica]/pratica-remoto.git [pasta-da-pratica]/ambiente-b
Cloning into '[pasta-da-pratica]/ambiente-b'...
done.
$ git config user.name Laura Ferreira
$ git config user.email 205853177+laurafsv@users.noreply.github.com
$ git add README.md
$ git commit -m Altera o título do README no ambiente A
[main ede22d8] Altera o título do README no ambiente A
 1 file changed, 1 insertion(+), 1 deletion(-)
$ git add README.md
$ git commit -m Altera o título do README no ambiente B
[main 89051c0] Altera o título do README no ambiente B
 1 file changed, 1 insertion(+), 1 deletion(-)
$ git push origin main
To [pasta-da-pratica]/pratica-remoto.git
   5aa9f0e..ede22d8  main -> main
$ git push origin main
To [pasta-da-pratica]/pratica-remoto.git
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to '[pasta-da-pratica]/pratica-remoto.git'
hint: Updates were rejected because the remote contains work that you do not
hint: have locally. This is usually caused by another repository pushing to
hint: the same ref. If you want to integrate the remote changes, use
hint: 'git pull' before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
$ git pull --no-rebase origin main
Auto-merging README.md
CONFLICT (content): Merge conflict in README.md
Automatic merge failed; fix conflicts and then commit the result.
From [pasta-da-pratica]/pratica-remoto
 * branch            main       -> FETCH_HEAD
   5aa9f0e..ede22d8  main       -> origin/main
$ git add README.md
$ git commit -m Resolve conflito no título do README
[main f2723af] Resolve conflito no título do README
$ git push origin main
To [pasta-da-pratica]/pratica-remoto.git
   ede22d8..f2723af  main -> main
$ git pull --no-rebase origin main
Updating ede22d8..f2723af
Fast-forward
 README.md | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)
From [pasta-da-pratica]/pratica-remoto
 * branch            main       -> FETCH_HEAD
   ede22d8..f2723af  main       -> origin/main
```
