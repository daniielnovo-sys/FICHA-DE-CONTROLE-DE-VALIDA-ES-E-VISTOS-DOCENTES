# Especificação de Requisitos — TechFlow Core

## Requisitos Funcionais (RF)
- **RF01 — Cadastrar demanda:** O sistema deve permitir registrar uma nova demanda solicitando título, nome do solicitante, nível de prioridade (Baixa, Média ou Alta) e CEP, atribuindo automaticamente um ID único e o status inicial "Aberta".
- **RF02 — Listar demandas:** O sistema deve exibir todas as demandas cadastradas no terminal, apresentando ID, título, solicitante, prioridade, cidade, CEP e status atual, ou informar caso a lista esteja vazia.
- **RF03 — Buscar demanda:** O sistema deve possibilitar a pesquisa de demandas pelo número de ID exato ou por trecho do título (sem diferenciar letras maiúsculas e minúsculas).
- **RF04 — Atualizar status:** O sistema deve permitir localizar uma demanda pelo ID e alterar seu status entre "Aberta", "Em andamento" e "Finalizada".
- **RF05 — Excluir demanda:** O sistema deve remover uma demanda existente a partir do seu ID, exigindo uma confirmação explícita (S/N) do usuário antes de apagar o registro.
- **RF06 — Consultar CEP e cotação:** O sistema deve consultar a API ViaCEP para preencher automaticamente a cidade a partir do CEP informado e consultar a cotação atual do Dólar (USD-BRL) via AwesomeAPI.

## Requisitos Não Funcionais (RNF)
- **RNF01 — Segurança:** O sistema deve tratar entradas inválidas e falhas de rede com blocos `try/except`, impedindo que o programa encerre inesperadamente.
- **RNF02 — Integridade:** Cada demanda deve receber um identificador (`id`) único, e campos obrigatórios (título, solicitante, prioridade e CEP) não podem ser salvos vazios.
- **RNF03 — Usabilidade:** A interface CLI deve apresentar menus numerados objetivos e mensagens claras de sucesso, alerta ou erro para orientar o usuário.
- **RNF04 — Desempenho:** Todas as operações locais em memória (cadastro, listagem, busca, edição e exclusão) devem responder em menos de 1 segundo.
- **RNF05 — Portabilidade e Ambiente:** O sistema deve utilizar exclusivamente bibliotecas nativas do Python (`urllib.request`, `json`, `os`, `datetime`), dispensando permissões de administrador no laboratório.