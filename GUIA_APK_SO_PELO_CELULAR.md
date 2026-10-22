# InvestAnalyzer — gerar APK usando somente o celular Android

Este pacote inclui o código do app e um fluxo de build na nuvem usando GitHub Actions. Você não precisa instalar Android Studio no celular.

## Passo a passo pelo navegador do celular

1. Crie ou entre na sua conta em https://github.com
2. Crie um repositório novo chamado `InvestAnalyzerAndroid`. Para uso pessoal, escolha **Private**.
3. Abra o repositório e use **Add file > Upload files**. Envie o conteúdo deste ZIP extraído. O arquivo `.github/workflows/android.yml` precisa ficar exatamente nesse caminho no repositório.
   - Se o GitHub móvel não permitir enviar pastas ocultas, crie a pasta `.github`, dentro dela `workflows`, e envie `android.yml` para lá.
   - A estrutura da raiz precisa conter `settings.gradle.kts`, `build.gradle.kts`, a pasta `app/` e a pasta `.github/`.
4. Faça commit para a branch `main`.
5. Abra a aba **Actions** do repositório. Se aparecer um aviso para habilitar Actions, habilite.
6. Selecione **Build InvestAnalyzer APK** e toque em **Run workflow** se o build não iniciar automaticamente após o commit.
7. Aguarde a execução terminar com marca verde. Abra a execução, desça até **Artifacts** e baixe `InvestAnalyzer-debug-APK`.
8. O arquivo baixado é um ZIP de artefato. Extraia-o no celular para obter `app-debug.apk`.
9. Toque no APK para instalar. O Android pode pedir autorização para instalar apps dessa origem; só autorize se você estiver no seu próprio repositório e reconhecer o arquivo gerado.

## Segurança e limitações

- O repositório contém código-fonte, não seus investimentos. Ainda assim, mantenha-o privado para uso pessoal.
- Não publique sua chave da Alpha Vantage no código ou no GitHub. A versão atual permite digitá-la na tela do app, mas não a armazena.
- O APK de debug é para teste pessoal. Antes de distribuir, seria necessário configurar uma versão de release assinada.
- O primeiro build pode falhar por incompatibilidade futura das ferramentas ou por erro no código. Se isso acontecer, envie a mensagem/log de erro para corrigirmos.
- O módulo de ações dos EUA depende de chave da Alpha Vantage e dos limites da API. Dados financeiros podem atrasar.
- A versão inicial ainda não contém o motor fundamentalista completo; ela é a base do app e da consulta de cotações. Não trate cotações como recomendação de investimento.

## Estrutura essencial
- `app/src/main/java/com/investanalyzer/app/MainActivity.kt`: interface e consultas iniciais
- `app/build.gradle.kts`: dependências Android
- `.github/workflows/android.yml`: build automático na nuvem
