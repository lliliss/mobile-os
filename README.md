# Mobile OS - Prevenir

Aplicativo mobile (Android e iOS) para gerenciamento de Ordens de Serviço da **Prevenir Extintores**, empresa especializada em instalações elétricas e serviços de combate a incêndio.

Permite que técnicos e administradores abram, acompanhem e finalizem O.S. diretamente do celular, consumindo a [API OS](https://github.com/lliliss/api-os).

---

## Estrutura do Projeto

```
mobile-os/
├── app/                  → Telas e rotas (Expo Router)
├── assets/               → Imagens, ícones e fontes
├── components/           → Componentes reutilizáveis
├── constants/            → Cores, temas e valores fixos
├── hooks/                → Hooks personalizados
├── services/             → Comunicação com a API
├── .env.example          → Modelo das variáveis de ambiente
├── app.json              → Configuração do Expo
├── package.json
└── README.md
```

---

## Funcionalidades principais

- **Login** com autenticação via JWT
- **Listagem de O.S.** filtrada por perfil (Admin vê todas, Técnico vê as atribuídas a ele)
- **Abertura de O.S.** com cliente, tipo de serviço, prioridade e descrição
- **Detalhe da O.S.** com histórico de status
- **Alteração de status** (Em andamento, Aguardando peça, Concluída)
- **Finalização** com descrição do serviço realizado
- **Gestão de clientes e técnicos** (perfil Admin)

---

## Stack

| Camada | Tecnologia |
|---|---|
| Framework | React Native |
| Plataforma | Expo |
| Linguagem | TypeScript |
| Navegação | Expo Router |
| Build | EAS Build |

---

## Pré-requisitos

- Node.js (versão LTS)
- App **Expo Go** no celular ([Android](https://play.google.com/store/apps/details?id=host.exp.exponent) / [iOS](https://apps.apple.com/app/expo-go/id982107779))
- [API OS](https://github.com/lliliss/api-os) rodando localmente

**Opcionais:**

- Android Studio, para usar o emulador Android
- Xcode (somente macOS), para usar o simulador iOS

---

### 1. Instalar as dependências

```bash
npm install
```

---

### 2. Configurar as variáveis de ambiente

Crie o arquivo `.env` na raiz do projeto com base no `.env.example`:

```bash
cp .env.example .env
```

```env
EXPO_PUBLIC_API_URL=http://localhost:8081
```

> Use o **IP da sua máquina na rede**, e não `localhost`. O celular é outro dispositivo e não enxerga o `localhost` do computador.

#### Descobrindo o IP local

**Windows:**

```powershell
ipconfig
```

Procure por **Endereço IPv4** no adaptador Wi-Fi (ex: `192.168.0.10`).

**macOS:**

```bash
ipconfig getifaddr en0
```

> O `.env` **nunca** deve ser commitado. Ele já está no `.gitignore`.

---

### 3. Rodar o app

```bash
npx expo start
```

- **Celular:** escaneie o QR Code com o Expo Go (Android) ou com a câmera (iOS)
- **Emulador Android:** pressione `a` no terminal
- **Simulador iOS:** pressione `i` no terminal (somente macOS)

> O celular e o computador precisam estar **na mesma rede Wi-Fi**.

Se o app não conectar à API, tente rodar com túnel:

```bash
npx expo start --tunnel
```

---

## Qualidade de código

```bash
npx expo lint
```

---

## Gerando os builds

Instale e faça login no EAS:

```bash
npm install -g eas-cli
eas login
```

Gere os builds:

```bash
eas build --platform android
eas build --platform ios
```

> O build de iOS exige uma conta Apple Developer.

---

## Branches

| Branch | Uso |
|---|---|
| `main` | Versão estável |
| `develop` | Desenvolvimento |

---

## Equipe

| Nome | Papel |
|---|---|
| Alice Ferreira Correia | Analista de Sistema / Desenvolvedora Mobile e Full-Stack|

---

## Tecnologias

- React Native
- Expo
- TypeScript
- Expo Router
- EAS Build

---

## 📄 Licença

© 2026 lliliss. Todos os direitos reservados.