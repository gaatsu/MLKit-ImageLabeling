# VisionAI

Um aplicativo inteligente para classificação de imagens com IA, utilizando o Google ML Kit e tradução automática dos rótulos para português via API.

## Funcionalidades

- Captura de imagens pela câmera ou seleção da galeria
- Classificação automática de objetos na imagem
- Tradução dos rótulos do inglês para português via API
- Exibição dos resultados com porcentagem de confiança e animações
- Interface moderna, elegante e intuitiva
- Animações de carregamento fluidas
- Design responsivo e adaptativo
- Identidade visual personalizada com ícone e tela de splash

## Tecnologias Utilizadas

- Flutter: Framework para desenvolvimento de aplicativos multiplataforma
- Google ML Kit: Biblioteca para implementação de recursos de Machine Learning
- Image Picker: Para captura e seleção de imagens
- Translator API: Para tradução automática em tempo real
- Material Design 3: Para a criação da interface do usuário
- Google Fonts: Para fontes personalizadas
- Flutter Native Splash: Para personalização da tela de inicialização
- Flutter Launcher Icons: Para personalização do ícone do aplicativo

## Implementação

O aplicativo foi desenvolvido seguindo uma arquitetura simples, utilizando o Flutter como base e integrando o ML Kit para classificação de imagens. Abaixo são detalhadas as principais etapas de implementação:

### 1. Configuração do Projeto

O projeto foi configurado com as seguintes dependências:
- `image_picker`: Para acessar a câmera e a galeria de fotos
- `google_mlkit_image_labeling`: Para classificação de objetos em imagens
- `translator`: Para tradução automática dos rótulos
- `google_fonts`: Para integração da fonte Poppins
- `flutter_launcher_icons`: Para personalização do ícone do aplicativo
- `flutter_native_splash`: Para personalização da tela de inicialização

Além disso, foram configuradas permissões específicas:
- Android: Permissões para câmera, armazenamento e internet
- iOS: Descrições de uso para câmera e biblioteca de fotos

### 2. Interface do Usuário

A interface foi desenvolvida com componentes Material Design 3, incluindo:
- Área para visualização da imagem com sombra elevada e bordas arredondadas
- Botões modernos com ícones e animações de toque
- Visualização dos resultados com barras de progresso animadas
- Indicadores de carregamento durante o processamento
- Gradientes suaves e esquemas de cores harmônicos
- Animações de transição entre estados do aplicativo
- Feedback visual durante a tradução e processamento
- Identidade visual personalizada (ícone e tela de splash)
- Tipografia moderna com a fonte Poppins

### 3. Processamento de Imagens

O processamento das imagens é realizado em algumas etapas principais:
1. Captura/seleção da imagem usando o `image_picker`
2. Conversão da imagem para o formato compatível com o ML Kit
3. Inicialização do classificador de imagens com um limite de confiança de 50%
4. Processamento da imagem e obtenção dos rótulos (labels)
5. Tradução dos rótulos de inglês para português usando a API do Google Translator
6. Exibição dos resultados ordenados por confiança com animações fluidas

### 4. Sistema de Tradução

Para implementar a tradução dos rótulos do inglês para o português, foi utilizada uma abordagem eficiente e em tempo real:

1. Integração com a API do Google Translator para tradução automática de todos os rótulos

2. Implementação de um sistema de cache (`Map<String, String>`) para armazenar traduções já realizadas, melhorando a performance e reduzindo requisições repetidas à API

3. Exibição de indicador visual durante o processo de tradução, informando ao usuário que a tradução está em andamento

4. Exibição do rótulo traduzido como título principal e do rótulo original em inglês em tamanho menor como referência

Esta abordagem permite a tradução de qualquer rótulo que o ML Kit (que possui mais de 400 labels no total) possa retornar, garantindo uma experiência completa para usuários brasileiros e eliminando a necessidade de manter um dicionário estático.

### 5. Tratamento de Erros

O aplicativo implementa um sistema robusto de tratamento de erros:
- Validação da seleção de imagens
- Verificação do estado de montagem (mounted) para evitar problemas com setState
- Exibição de mensagens de erro visualmente atraentes quando o processamento falha
- Tratamento de erros durante a tradução, mantendo o rótulo original em caso de falha
- Feedback visual claro para o usuário em cada etapa do processo

### 6. Personalização da Identidade Visual

Para criar uma experiência de marca completa, o aplicativo implementa:
- Ícone personalizado para Android e iOS
- Tela de splash personalizada
- Esquema de cores consistente
- Tipografia personalizada com a fonte Poppins
- Nome e identidade visual "VisionAI"

## Fluxo de Funcionamento

1. O usuário inicia o aplicativo e visualiza a tela de splash personalizada
2. Após carregar, a tela principal é exibida com design moderno
3. O usuário pode selecionar uma imagem da galeria ou capturar uma nova com a câmera
4. Durante o processamento da imagem, é exibida uma animação de carregamento
5. Os resultados da classificação são exibidos com animações suaves, mostrando os objetos identificados traduzidos para português e barras de progresso animadas com o percentual de confiança
6. Se nenhum objeto for identificado com mais de 50% de confiança, uma mensagem visualmente atraente é mostrada

## Melhorias Implementadas

1. **Tradução em Tempo Real**: Implementada a API de tradução online para traduzir automaticamente todos os rótulos, substituindo completamente o sistema de mapa estático

2. **Interface Moderna**: Design atualizado com elementos visuais modernos, sombras, gradientes e cantos arredondados

3. **Animações Fluidas**: Adicionadas animações de carregamento, transições suaves e feedback visual para todas as ações

4. **Sistema de Cache**: Implementado cache para traduções já realizadas, melhorando a performance

5. **Adaptação ao Tema**: Interface adaptativa que responde ao tema do sistema

6. **Remoção da Banner de Debug**: Banner de debug removido para uma aparência mais limpa e profissional

7. **Feedback Visual**: Adição de indicadores visuais para todas as operações em andamento

8. **Orientação de Tela**: Configuração de orientação fixa para melhor experiência do usuário

9. **Identidade Visual**: Implementação de ícone personalizado e tela de splash

10. **Novo Nome**: Renomeado para "VisionAI" para melhor refletir o propósito do aplicativo

## Possíveis Melhorias Futuras

Algumas melhorias que poderiam ser implementadas em versões futuras:

1. **Classificação Offline**: Implementar a possibilidade de classificação sem conexão com a internet, baixando modelos para uso local.

2. **Modelos Personalizados**: Permitir o uso de modelos de machine learning personalizados ou treinados para domínios específicos.

3. **Histórico de Imagens**: Adicionar a capacidade de salvar o histórico de imagens analisadas e seus resultados.

4. **Classificação em Tempo Real**: Implementar a classificação em tempo real usando o stream da câmera.

5. **Múltiplos Idiomas**: Adicionar suporte para diferentes idiomas nos resultados da classificação.

6. **Compartilhamento de Resultados**: Permitir o compartilhamento dos resultados da classificação em redes sociais.

7. **Integração com Firebase**: Armazenar resultados em nuvem e permitir análises mais detalhadas.

8. **Modo Escuro**: Implementar tema escuro completo para o aplicativo.

9. **Acessibilidade**: Melhorar os recursos de acessibilidade para usuários com necessidades especiais.

10. **Reconhecimento de Faces**: Adicionar recursos de reconhecimento facial.

## Resolução de Problemas

### Configuração do NDK

Durante o desenvolvimento, foi necessário ajustar a versão do Android NDK para garantir compatibilidade com as dependências do projeto. Isso foi feito de duas maneiras:

1. Adicionando a especificação da versão do NDK no arquivo `gradle.properties`:
   ```
   android.ndkVersion=27.0.12077973
   ```

2. Definindo a versão do NDK diretamente no arquivo `build.gradle.kts`:
   ```kotlin
   android {
       ndkVersion = "27.0.12077973"
       ...
   }
   ```

## Como Executar

1. Clone o repositório
2. Execute `flutter pub get` para instalar as dependências
3. Execute `flutter pub run flutter_launcher_icons` para gerar os ícones
4. Execute `flutter pub run flutter_native_splash:create` para gerar a tela de splash
5. Conecte um dispositivo ou inicie um emulador
6. Execute `flutter run` para iniciar o aplicativo

## Requisitos do Sistema

- Flutter SDK: 3.0.0 ou superior
- Dart SDK: 2.17.0 ou superior
- Android SDK: API 21+ (Android 5.0 ou superior)
- iOS: iOS 11.0 ou superior
- Android NDK: 27.0.12077973 (específico para compatibilidade)
- Conexão com internet (para tradução em tempo real)
