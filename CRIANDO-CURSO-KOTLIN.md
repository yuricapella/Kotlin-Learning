# Iniciando um curso Kotlin com Gradle

Guia rápido para criar um novo projeto Kotlin básico usando Gradle.

## Pré-requisitos

Verifique se Java e Gradle estão instalados:

```bash
java -version
gradle -v
```

Se o Gradle não estiver instalado no macOS:

```bash
brew install gradle
```

## Criar o projeto

Entre na pasta onde o curso será criado e rode:

```bash
mkdir nome-do-curso
cd nome-do-curso
gradle init --type basic --dsl kotlin
```

Durante o `gradle init`, use:

```text
Continue? yes
Project name: Enter
Generate build using new APIs and behavior? no
```

## Gerar o Gradle Wrapper

```bash
gradle wrapper
```

Isso cria:

```text
gradlew
gradlew.bat
gradle/wrapper/
```

## Configurar Kotlin

No arquivo `build.gradle.kts`, mantenha a configuração abaixo:

```kotlin
plugins {
    kotlin("jvm") version "2.2.21"
}

repositories {
    mavenCentral()
}

dependencies {
    testImplementation(kotlin("test"))
}

kotlin {
    jvmToolchain(21)
}
```

## Validar o build

```bash
./gradlew build
```

Se der erro de permissão:

```bash
chmod +x gradlew
./gradlew build
```

## Rodar arquivos Kotlin

Crie arquivos `.kt` dentro do projeto e execute pelo `tasks.json` do VS Code.

Atalho padrão:

```text
Cmd + Shift + B
```

Atalho opcional configurado:

```text
F5
```

Cada arquivo pode ter seu próprio `main`:

```kotlin
fun main() {
    println("Olá, Kotlin!")
}
```

## Arquivos que devem ser commitados

```text
.gitattributes
.gitignore
build.gradle.kts
gradle.properties
gradle/libs.versions.toml
gradle/wrapper/gradle-wrapper.jar
gradle/wrapper/gradle-wrapper.properties
gradlew
gradlew.bat
settings.gradle.kts
```

## Resumo

```bash
mkdir nome-do-curso
cd nome-do-curso
gradle init --type basic --dsl kotlin
gradle wrapper
./gradlew build
```