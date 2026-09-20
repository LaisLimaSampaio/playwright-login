Requisito testado: login com credenciais válidas deve autenticar; credenciais inválidas devem ser rejeitadas sem revelar qual dado está incorreto.

Precondições:
- conta ana@exemplo.com já existe e está ativa
- aplicação disponível em http://localhost:3000/login (subida automaticamente pelo Playwright via webServer)
- cada teste inicia sem sessão/cookies herdados

Dados usados (cenário válido): e-mail ana@exemplo.com, senha SenhaSegura123!
Resultado esperado: redireciona para /conta; título 'Minha conta' visível.

Dados usados (cenário inválido): e-mail ana@exemplo.com, senha senha-incorreta
Resultado esperado: permanece em /login; mensagem 'E-mail ou senha inválidos'; acesso direto a /conta continua bloqueado.

Locators usados: getByLabel('E-mail'), getByLabel('Senha'), getByRole('button', name: 'Entrar'), getByRole('alert'), getByRole('heading', name: 'Minha conta')

Comando executado: npx playwright test --project=chromium --headed
Resultado da execução: 2 testes aprovados / 0 testes reprovados

Falha provocada e investigação no UI Mode: [ainda não realizado -- trocar a senha válida por uma errada em tests/login.spec.ts, rodar 'npx playwright test --ui' e descrever aqui o passo em que a asserção falhou]

Checklist:
- [x] requisito e resultado esperado definidos
- [x] ambiente autorizado e endereço configurado
- [x] dados controlados
- [x] teste independente
- [x] locators semânticos e únicos
- [x] ações aguardadas com await
- [x] asserções web específicas
- [x] efeitos importantes verificados
- [x] execução em navegador relevante
- [x] segredos fora do código e do repositório
