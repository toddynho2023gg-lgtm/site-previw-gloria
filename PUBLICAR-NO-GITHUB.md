# Publicar pelo GitHub Codespaces

Coloque `gloria-odontologia-primeira-versao.zip` na raiz do repositório,
abra o terminal do Codespaces e execute o bloco abaixo inteiro. Ele entra na
raiz correta, extrai por uma pasta temporária, copia inclusive arquivos ocultos,
remove o ZIP, valida o projeto, cria o commit e envia a branch `main`.

```bash
set -euo pipefail

cd "$(git rev-parse --show-toplevel)"

gloria_zip="gloria-odontologia-primeira-versao.zip"
test -f "$gloria_zip"

gloria_extract_dir="$(mktemp -d)"
unzip -o "$gloria_zip" -d "$gloria_extract_dir"
cp -a "$gloria_extract_dir"/. .

rm -r "$gloria_extract_dir"
rm -f "$gloria_zip"

test -f package.json
test -d app
test -d public
test -d src

npm ci
npm test
npm run lint
npm run build

git config user.name >/dev/null 2>&1 || git config user.name "toddynho2023gg-lgtm"
git config user.email >/dev/null 2>&1 || git config user.email "toddynho2023gg-lgtm@users.noreply.github.com"

git add -A
git diff --cached --quiet || git commit -m "Publica site Glória Odontologia"
git branch -M main
git push -u origin main

git status
```

O resultado final deve terminar com a branch sincronizada e a mensagem
`nothing to commit, working tree clean`.
