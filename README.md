# Flutter App — Login, Cadastro e Tela Principal

Projeto Flutter com três telas e navegação implementada via `Navigator` com rotas nomeadas.

## Estrutura do Projeto

```
lib/
├── main.dart                  # Ponto de entrada + definição das rotas
└── screens/
    ├── login_screen.dart      # Tela de Login
    ├── cadastro_screen.dart   # Tela de Cadastro
    └── tela_principal.dart    # Tela Principal
```

## Navegação

| De → Para                        | Método utilizado              | Pilha limpa? |
|----------------------------------|-------------------------------|:------------:|
| Login → Tela Principal           | `pushReplacementNamed`        | ✅ Sim        |
| Login → Cadastro                 | `pushNamed`                   | ❌ Não        |
| Cadastro → Tela Principal        | `pushReplacementNamed`        | ✅ Sim        |
| Cadastro → Login (botão Voltar)  | `pop`                         | ❌ Não        |
| Tela Principal → Login (Sair)    | `pushReplacementNamed`        | ✅ Sim        |

## Como executar

```bash
flutter pub get
flutter run
```

## Telas

### Tela de Login (`/login`)
- Campos: Email e Senha
- Botão **Entrar** → navega para `/principal` (substituindo a rota, sem volta)
- Link **Não tem conta? Cadastre-se** → navega para `/cadastro`

### Tela de Cadastro (`/cadastro`)
- Campos: Nome Completo, Email, Senha, Confirmar Senha
- Botão **Voltar** → retorna para `/login` via `pop`
- Botão **Cadastrar** → navega para `/principal` (substituindo a rota)

### Tela Principal (`/principal`)
- AppBar com título "Tela Principal" e ícones de ação
- Banner de boas-vindas com gradiente
- Cards de funcionalidades: Dashboard, Menu, Configurações
- Botão **Sair** → navega para `/login` (substituindo a rota, sem volta)
- **PopScope** desabilita o botão voltar do dispositivo (Android/iOS)
