# Explorando Práticas de Teste

Neste exercício, vamos explorar práticas de teste em sistemas reais utilizando a ferramenta [TestMiner](https://andrehora.github.io/testminer).

O TestMiner permite visualizar e analisar testes de software em repositórios do GitHub, fornecendo dados sobre como os projetos organizam seus testes, como eles evoluem entre versões e quais bibliotecas de teste são utilizadas.
Explore a ferramenta antes de começar para se familiarizar com seu funcionamento.

---

## Passo 1: Selecionar um repositório

Escolha um repositório real que possua testes escritos na linguagem de sua preferência.
Abaixo estão alguns links para ajudá-lo a encontrar projetos interessantes:

- **Python:** https://github.com/topics/python?l=python
- **JavaScript:** https://github.com/topics/javascript?l=javascript
- **TypeScript:** https://github.com/topics/typescript?l=typescript
- **Java:** https://github.com/topics/java?l=java

## Passo 2: Explorar o repositório selecionado

Busque o repositório escolhido no [TestMiner](https://andrehora.github.io/testminer) e analise os dados de teste gerados pela ferramenta.

## Passo 3: Explicar uma prática de teste

Com base nos dados obtidos, selecione uma prática ou dado de teste relevante e explique-o com suas próprias palavras.

---

## Instruções de entrega

1. Faça um `fork` deste repositório (saiba mais sobre forks [aqui](https://docs.github.com/pt/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo)).
2. Responda às questões abaixo diretamente neste arquivo `README.md` do seu fork. Pode adicionar imagens para enriquecer sua explicação.
3. No Moodle, submeta apenas a URL do seu fork.

---

## Respostas

**1. Repositório selecionado:** `<URL_DO_REPOSITÓRIO_AQUI>`

**2. Explicação:** `<SUA_EXPLICAÇÃO_AQUI>`


## Respostas

**1. Repositório selecionado:** `https://github.com/psf/requests`

**2. Explicação:**

### Prática analisada: Crescimento progressivo da suíte de testes entre versões

O repositório `psf/requests` é a biblioteca HTTP mais popular do Python (53.9k ⭐). A análise no TestMiner revela como a suíte de testes evoluiu de forma consistente ao longo das versões do projeto.

#### Estrutura atual (branch `main`)

| Categoria | Qtd |
|---|---|
| Source Files | 66 |
| Tests | 10 |
| Test Helpers | 12 |
| CI Tests | 1 |

Os 10 arquivos de teste cobrem áreas bem delimitadas: `adapters`, `hooks`, `lowlevel`, `requests`, `structures`, `utils`, entre outros. Os 12 Test Helpers fornecem infraestrutura de apoio (certificados SSL, servidor local, compatibilidade). Toda a suíte está organizada na pasta `tests/`, separada do código-fonte — prática que facilita manutenção e execução independente dos testes.

#### Histórico de testes por versão

| Versão | Arquivos de teste |
|---|---|
| 0.2.0 | 1 |
| 0.9.0 | 2 |
| 2.0.1 | 1 |
| 2.16.2 | 8 |
| 2.33.1 | 10 |

O projeto iniciou com apenas 1 arquivo de teste e chegou a 10 na versão atual. O salto mais expressivo ocorre entre as versões 2.0.1 e 2.16.2 — período de maior amadurecimento da biblioteca, quando funcionalidades como autenticação avançada, proxies e SSL foram consolidadas e ganharam cobertura dedicada.

O CI Test (`run`) só aparece a partir da versão 2.33.1, evidenciando a adoção recente de integração contínua via GitHub Actions para execução automática dos testes a cada commit.

#### Conclusão

O crescimento da suíte acompanhando o produto demonstra maturidade técnica: cada nova área funcional ganhou seu próprio arquivo de teste. Dado que `requests` é usada por milhões de projetos, essa disciplina é essencial para garantir que regressões sejam detectadas antes de chegarem aos usuários finais.
