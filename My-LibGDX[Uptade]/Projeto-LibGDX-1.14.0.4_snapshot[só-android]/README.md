# Projeto LibGDX - Android Only

Um projeto [libGDX](https://libgdx.com/) configurado exclusivamente para desenvolvimento Android.

Este projeto foi gerado com [gdx-liftoff](https://github.com/libgdx/gdx-liftoff) e configurado para focar apenas na plataforma Android, removendo dependências e configurações de outras plataformas.

## Plataformas

- `core`: Módulo principal com a lógica do aplicativo compartilhada por todas as plataformas.
- `android`: Plataforma móvel Android. Requer Android SDK configurado.

**Nota:** Este projeto foi configurado para suportar **apenas Android**. As seguintes plataformas foram removidas:
- ~~LWJGL3 (Desktop)~~
- ~~iOS~~
- ~~HTML/Web~~

## Gradle

Este projeto usa [Gradle](https://gradle.org/) para gerenciar dependências.
O wrapper do Gradle está incluído, então você pode executar tarefas do Gradle usando `gradlew.bat` ou `./gradlew`.

Tarefas úteis do Gradle e flags:

- `--continue`: ao usar esta flag, os erros não impedirão a execução das tarefas.
- `--daemon`: graças a esta flag, o daemon do Gradle será usado para executar as tarefas escolhidas.
- `--offline`: ao usar esta flag, arquivos de dependência em cache serão usados.
- `--refresh-dependencies`: esta flag força a validação de todas as dependências. Útil para versões snapshot.
- `android:lint`: realiza validação do projeto Android.
- `android:assembleDebug`: compila o APK em modo debug.
- `android:assembleRelease`: compila o APK em modo release (requer configuração de keystore).
- `android:installDebug`: instala o APK debug em um dispositivo/emulador conectado.
- `build`: compila fontes e arquivos de cada projeto.
- `cleanEclipse`: remove dados do projeto Eclipse.
- `cleanIdea`: remove dados do projeto IntelliJ.
- `clean`: remove pastas `build`, que armazenam classes compiladas e arquivos construídos.
- `eclipse`: gera dados do projeto Eclipse.
- `idea`: gera dados do projeto IntelliJ.
- `test`: executa testes unitários (se houver).

Note que a maioria das tarefas que não são específicas de um único projeto podem ser executadas com o prefixo `name:`, onde `name` deve ser substituído pelo ID de um projeto específico.
Por exemplo, `core:clean` remove a pasta `build` apenas do projeto `core`.

## Requisitos

- JDK 17 ou superior
- Android SDK configurado
- Variável de ambiente `ANDROID_HOME` apontando para o diretório do Android SDK

## Como Executar

Para executar o projeto no Android:

1. Conecte um dispositivo Android ou inicie um emulador
2. Execute: `./gradlew android:installDebug` (Linux/Mac) ou `gradlew.bat android:installDebug` (Windows)
3. O aplicativo será instalado e iniciado no dispositivo/emulador
