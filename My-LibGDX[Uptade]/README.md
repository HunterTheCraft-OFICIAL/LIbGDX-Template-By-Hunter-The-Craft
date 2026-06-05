# 📦 Coleção de Projetos LibGDX

Este repositório contém dois projetos LibGDX configurados para diferentes propósitos e plataformas. Ambos foram gerados com [gdx-liftoff](https://github.com/libgdx/gdx-liftoff) e usam Gradle como gerenciador de dependências.

---

## 📋 Índice

1. [Visão Geral](#visão-geral)
2. [Projeto 1: Android Only (1.14.0.4-SNAPSHOT)](#projeto-1-android-only)
3. [Projeto 2: Multiplataforma Desktop (1.14.1.1)](#projeto-2-multiplataforma-desktop)
4. [Comparação entre Projetos](#comparação-entre-projetos)
5. [Requisitos Gerais](#requisitos-gerais)
6. [Links Úteis](#links-úteis)

---

## 🎯 Visão Geral

| Característica | Projeto 1 (Android) | Projeto 2 (Desktop) |
|----------------|---------------------|---------------------|
| **Versão LibGDX** | 1.14.0 (SNAPSHOT) | 1.14.1 (Estável) |
| **Plataformas** | Android apenas | LWJGL3, LWJGL2, Headless |
| **Linguagens** | Java | Java, Kotlin, Groovy, Scala |
| **Versão do Projeto** | 1.14.0.4-SNAPSHOT | 0.0.1 |
| **Nome do App** | gdx-liftoff-demo | Generic Logistics Enterprise |

---

## 📱 Projeto 1: Android Only

**Caminho:** `Projeto-LibGDX-1.14.0.4_snapshot[só-android]/`

### Descrição
Este projeto foi configurado exclusivamente para desenvolvimento Android. Inicialmente era multiplataforma, mas outras plataformas foram removidas para focar apenas no Android, que era o escopo necessário.

### Estrutura do Projeto

```
Projeto-LibGDX-1.14.0.4_snapshot[só-android]/
├── core/           # Módulo principal com lógica compartilhada
├── android/        # Plataforma Android
├── assets/         # Recursos do jogo (imagens, sons, etc.)
└── gradle/         # Configurações do Gradle
```

### Dependências Principais

- **LibGDX:** 1.14.0
- **Ashley:** 1.7.4 (Sistema ECS)
- **Box2DLights:** 1.5 (Iluminação 2D)
- **gdx-ai:** 1.8.2 (Inteligência Artificial)
- **gdx-box2d:** Física 2D
- **gdx-bullet:** Física 3D
- **gdx-freetype:** Renderização de fontes
- **gdx-controllers:** Suporte a controles

### Configurações Técnicas

- **Compile SDK:** 35
- **Min SDK:** 21 (Android 5.0+)
- **Target SDK:** 35
- **Java Compatibility:** 11
- **Android Gradle Plugin:** 8.9.3
- **AndroidX:** Habilitado

### Como Executar

1. **Pré-requisitos:**
   - JDK 17 ou superior
   - Android SDK configurado
   - Variável `ANDROID_HOME` apontando para o SDK

2. **Executar no dispositivo/emulador:**
   ```bash
   # Linux/Mac
   ./gradlew android:installDebug
   
   # Windows
   gradlew.bat android:installDebug
   ```

3. **Tarefas úteis:**
   ```bash
   ./gradlew android:assembleDebug    # Compila APK debug
   ./gradlew android:assembleRelease  # Compila APK release
   ./gradlew android:lint             # Análise estática do código
   ```

### Mais Informações
Veja o [README detalhado](./Projeto-LibGDX-1.14.0.4_snapshot%5Bs%C3%B3-android%5D/README.md) dentro da pasta do projeto.

---

## 🖥️ Projeto 2: Multiplataforma Desktop

**Caminho:** `Projeto-LibGDX-1.14.1.1[sem-android]/`

### Descrição
Este projeto foi configurado para suportar múltiplas plataformas desktop, incluindo LWJGL3 (primário), LWJGL2 (legado) e modo headless (sem interface gráfica). Ideal para desenvolvimento de jogos e aplicações desktop.

### Estrutura do Projeto

```
Projeto-LibGDX-1.14.1.1[sem-android]/
├── core/           # Módulo principal com lógica compartilhada
├── lwjgl3/         # Plataforma desktop primária (LWJGL3)
├── lwjgl2/         # Plataforma desktop legada (LWJGL2)
├── headless/       # Plataforma sem interface gráfica
├── assets/         # Recursos do jogo
└── gradle/         # Configurações do Gradle
```

### Dependências Principais

- **LibGDX:** 1.14.1
- **Kotlin:** 2.3.21
- **Groovy:** 5.0.4
- **Scala:** 3.8.2
- **LWJGL3:** 3.4.1
- **Ashley:** 1.7.4
- **Box2DLights:** 1.5
- **gdx-ai:** 1.8.2
- **gdx-tools:** Ferramentas LibGDX

### Plataformas Suportadas

| Plataforma | Módulo | Descrição |
|------------|--------|-----------|
| **LWJGL3** | `lwjgl3` | Plataforma desktop primária, recomendada |
| **LWJGL2** | `lwjgl2` | Plataforma desktop legada |
| **Headless** | `headless` | Sem interface gráfica (servidores, testes) |

### Configurações Técnicas

- **Java Compatibility:** 11
- **Kotlin JVM Target:** 11
- **Construo:** 2.1.0 (Empacotamento nativo)
- **Foojay Resolver:** 1.0.0 (Download automático de JDK)

### Como Executar

1. **Pré-requisitos:**
   - JDK 17 ou superior (download automático via Foojay)

2. **Executar aplicações:**
   ```bash
   # LWJGL3 (Recomendado)
   ./gradlew lwjgl3:run
   
   # LWJGL2
   ./gradlew lwjgl2:run
   
   # Headless
   ./gradlew headless:run
   ```

3. **Compilar JARs executáveis:**
   ```bash
   # JAR multiplataforma
   ./gradlew lwjgl3:jar
   
   # JARs específicos por plataforma
   ./gradlew lwjgl3:jarWin    # Apenas Windows
   ./gradlew lwjgl3:jarLinux  # Apenas Linux
   ./gradlew lwjgl3:jarMac    # Apenas macOS
   ```

4. **Criar distribuições nativas:**
   ```bash
   ./gradlew lwjgl3:distributeLinuxX64
   ./gradlew lwjgl3:distributeWinX64
   ./gradlew lwjgl3:distributeMacM1
   ./gradlew lwjgl3:distributeMacX64
   ```

### Recursos Especiais

- **Construo:** Cria executáveis nativos com JRE embutido
- **JARs Otimizados:** Opção de criar JARs menores para plataformas específicas
- **Multi-language:** Suporte a Kotlin, Groovy e Scala além de Java
- **Native Access:** Suporte a acesso nativo no Java 14+

### Mais Informações
Veja o [README detalhado](./Projeto-LibGDX-1.14.1.1%5Bsem-android%5D/README.md) dentro da pasta do projeto.

---

## ⚖️ Comparação entre Projetos

### Quando usar cada projeto?

**Use o Projeto 1 (Android) quando:**
- ✅ Desenvolver exclusivamente para Android
- ✅ Precisar de integração com APIs Android
- ✅ Quiser um projeto mais leve e focado
- ✅ Não precisar de suporte a desktop

**Use o Projeto 2 (Desktop) quando:**
- ✅ Desenvolver para Windows, macOS ou Linux
- ✅ Quiser criar executáveis nativos
- ✅ Precisar testar rapidamente sem emulador
- ✅ Desejar usar Kotlin, Groovy ou Scala
- ✅ Precisar de modo headless para servidores/testes

### Diferenças Técnicas

| Recurso | Projeto 1 | Projeto 2 |
|---------|-----------|-----------|
| Android | ✅ Sim | ❌ Não |
| Desktop | ❌ Não | ✅ Sim (3 plataformas) |
| Kotlin | ❌ Não | ✅ Sim |
| Groovy | ❌ Não | ✅ Sim |
| Scala | ❌ Não | ✅ Sim |
| JAR Executável | ❌ Não | ✅ Sim |
| Native Build | ❌ Não | ✅ Sim (Construo) |
| LibGDX Version | 1.14.0 | 1.14.1 |

---

## 🛠️ Requisitos Gerais

### Para ambos os projetos:
- **JDK:** 17 ou superior
- **Gradle:** Wrapper incluído (não precisa instalar)
- **IDE Recomendada:** IntelliJ IDEA ou Eclipse

### Específico Projeto 1 (Android):
- **Android SDK**
- **ANDROID_HOME** variável de ambiente configurada
- **Dispositivo Android** ou emulador

### Específico Projeto 2 (Desktop):
- Nenhum requisito adicional
- Download automático de JDK via Foojay (opcional)

---

## 🔗 Links Úteis

### Documentação Oficial
- [LibGDX](https://libgdx.com/)
- [gdx-liftoff](https://github.com/libgdx/gdx-liftoff)
- [Gradle](https://gradle.org/)

### Repositórios Relacionados
- [LIbGDX-Template-By-Hunter-The-Craft](https://github.com/HunterTheCraft-OFICIAL/LIbGDX-Template-By-Hunter-The-Craft)

### Ferramentas
- [Android Studio](https://developer.android.com/studio)
- [IntelliJ IDEA](https://www.jetbrains.com/idea/)
- [LWJGL3](https://www.lwjgl.org/)
- [Construo](https://github.com/fourlastor-alex/construo)

---

## 📝 Notas

- Ambos os projetos usam repositórios Maven Central, Sonatype Snapshots e JitPack
- O Projeto 1 usa versão SNAPSHOT do LibGDX (1.14.0.4-SNAPSHOT)
- O Projeto 2 usa versão estável mais recente (1.14.1)
- Ambos incluem geração automática de `assets.txt` listando todos os arquivos de assets

---

**Autor:** HunterTheCraft  
**Licença:** Consulte os arquivos de licença em cada subprojeto
