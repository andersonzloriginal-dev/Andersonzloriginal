# InvestAnalyzer Android — projeto inicial

Aplicativo Android nativo em Kotlin + Jetpack Compose. Este ZIP é o **código-fonte inicial**, não um APK compilado.

## O que já existe nesta base
- Interface mobile em tema escuro.
- Campo para pesquisar ticker.
- Integração inicial com a brapi para cotações da B3 (o sandbox sem token cobre PETR4, VALE3, MGLU3 e ITUB4).
- Estrutura inicial para consultar uma cotação dos EUA via Alpha Vantage, usando uma chave que você deverá obter e configurar.
- Estados de carregamento e mensagens de erro, sem fabricar cotações.

## O que ainda não está implementado
- Análise fundamentalista completa e cálculo de preço justo.
- Carteira persistente, favoritos, alertas e gráficos históricos.
- Serviço intermediário/backend para proteger chaves de API.
- Testes automatizados, ícone final, política de privacidade e assinatura de release.

## Como abrir
1. Baixe e extraia o ZIP num computador.
2. Instale o Android Studio e o Android SDK.
3. Abra a pasta `InvestAnalyzerAndroid` no Android Studio e aguarde a sincronização do Gradle.
4. Rode em um emulador ou conecte o Android com Depuração USB.
5. Para gerar APK de teste: **Build > Build APK(s)**.

A geração de APK assinável de release é feita em **Build > Generate Signed Bundle / APK**.

## Fontes de dados planejadas
- B3: https://brapi.dev/docs — o plano gratuito informa limite mensal e delay; confirme os termos atuais antes de uso contínuo.
- EUA: https://www.alphavantage.co/documentation/ — requer API key gratuita; o limite gratuito publicado é restrito (25 requisições/dia na documentação consultada).

## Configuração Alpha Vantage
A primeira versão inclui o esqueleto do endpoint Global Quote. Para evitar colocar segredo no código, a chave não vem embutida. A integração dos EUA ainda deve ser concluída com uma tela de configuração segura ou, preferencialmente, backend próprio.

## Importante
Os dados são informativos e podem ter atraso. Este protótipo não executa ordens e não deve ser usado como única base para decisões de investimento.
