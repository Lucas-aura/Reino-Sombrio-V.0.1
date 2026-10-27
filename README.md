# Reino Sombrio — projeto Android

Este projeto empacota o jogo HTML incluído em `app/src/main/assets/index.html` em um app Android de tela cheia e orientação paisagem, usando WebView local.

## Gerar APK usando apenas o celular (compilação na nuvem)

Este pacote inclui um fluxo do GitHub Actions que compila um APK de teste na nuvem. Você precisará de uma conta GitHub e conexão com a internet.

1. No navegador, entre em https://github.com e crie um repositório novo chamado `ReinoSombrio`.
2. Extraia este ZIP se o site/gerenciador de arquivos permitir. Se não permitir, use a opção de upload do GitHub para enviar os arquivos e pastas do projeto. A pasta `.github/workflows/build-apk.yml` é importante; confirme que ela foi enviada.
3. Envie os arquivos para o branch `main` (ou `master`). O fluxo começa automaticamente quando houver um push para esse branch.
4. No repositório, abra a aba **Actions** e selecione **Build Reino Sombrio APK**. Se necessário, toque em **Run workflow**.
5. Aguarde o fluxo terminar com marca verde. Abra a execução concluída, desça até **Artifacts** e baixe `Reino-Sombrio-APK-de-teste`.
6. Extraia o ZIP do artefato e toque em `app-debug.apk` no Android para instalar. O sistema pode pedir que você permita instalar apps dessa fonte; só prossiga se reconhece o arquivo que acabou de gerar.

## O que este APK significa

- É um APK **de teste**, assinado com a chave de depuração gerada pela compilação.
- Não é um pacote pronto para a Google Play Store. Para publicar, será necessário gerar um AAB de lançamento com uma chave de assinatura mantida em segurança e cumprir as exigências atuais do Play Console.
- Teste no aparelho o menu, história, controles, áudio, salvamento, todos os mundos e Free Battle. Não foi possível testar o jogo em aparelho físico neste ambiente.

## Requisitos técnicos

- Android Studio/Gradle não são necessários no celular para o fluxo em nuvem, mas é necessária uma conta GitHub para executar o workflow.
- A compilação usa Java 17, Gradle 8.9 e Android SDK 35.
- O app executa o HTML localmente; não precisa de conexão à internet durante o jogo, desde que todos os recursos usados estejam incluídos no HTML.
