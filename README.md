# MiniGames

브라우저에서 바로 실행되는 2D 미니게임들을 모아 제공하는 프로젝트입니다.
초기 대상은 모바일 브라우저 우선이며, 데스크톱 브라우저에서도 동일한 핵심
플레이 흐름을 사용할 수 있게 설계합니다.

## Project Direction

- Browser-first 2D mini-game hub
- Touch-first mobile UX with desktop compatibility
- Fast load and short-session gameplay
- Shared shell plus modular game integrations
- Performance, accessibility, analytics, and release QA as required gates

## Working Rules

- Project constitution: `.specify/memory/constitution.md`
- Feature flow: `/speckit.specify` -> `/speckit.plan` -> `/speckit.tasks`
- Every user-facing change must define browser support, control model, performance
  targets, analytics events, and a rollback path

## Suggested Initial Structure

```text
apps/
└── web/
    ├── src/
    │   ├── app/
    │   ├── catalog/
    │   ├── games/
    │   └── shared/
    └── tests/

packages/
├── game-sdk/
├── platform-services/
└── ui/

tests/
├── contract/
├── integration/
└── smoke/
```
