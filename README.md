# Engenharia_Software_2025-2_langextract_atividade3_parte1

# Análise de Integração Contínua (CI) – Projeto LangExtract

## 1. Introdução

A evolução contínua de sistemas de software exige mecanismos que garantam a qualidade e a estabilidade do código ao longo do tempo. Nesse contexto, a Integração Contínua (Continuous Integration – CI) surge como uma prática fundamental, permitindo que alterações no código sejam verificadas automaticamente, reduzindo riscos de regressão e facilitando a colaboração entre desenvolvedores.

Esta atividade tem como objetivo analisar a maturidade das práticas de CI de um projeto de software open source real, no qual a equipe atua como engenheiros de DevOps. A partir dessa análise, busca-se compreender como a automação influencia a manutenibilidade do sistema e a entrada de novos contribuidores no projeto.

---

## 2. Descrição do Projeto Avaliado

O projeto analisado nesta atividade é o **LangExtract**, um projeto open source mantido pela Google e disponibilizado na plataforma GitHub.

- **Repositório:** https://github.com/google/langextract

O LangExtract é uma biblioteca Python que utiliza *Large Language Models (LLMs)* para extrair informações estruturadas a partir de documentos de texto não estruturados, com base em instruções definidas pelo usuário. A biblioteca é aplicada em contextos como anotações clínicas ou relatórios textuais, identificando e organizando dados relevantes, garantindo que as informações extraídas correspondam fielmente ao texto original.

---

## 3. Metodologia de Investigação

A investigação do projeto foi realizada por meio de uma análise exploratória do repositório no GitHub, com foco nas práticas de Integração Contínua adotadas. Foram observados os seguintes aspectos:

- Existência do diretório `.github/workflows/`;
- Análise dos arquivos YAML de workflows;
- Verificação da aba **Actions** do GitHub;
- Observação do histórico de Pull Requests.

Essa abordagem permitiu mapear o fluxo atual de desenvolvimento e identificar o nível de automação presente no projeto.

---

## 4. Ferramentas de CI/CD Utilizadas

O projeto LangExtract utiliza o **GitHub Actions** como ferramenta de Integração Contínua (CI). Essa ferramenta é nativa da plataforma GitHub e permite a execução automática de tarefas em resposta a eventos como *push* e *pull request*, integrando-se diretamente ao fluxo de desenvolvimento do repositório.

---

## 5. Evidências Técnicas

Como evidência da utilização de CI, foram identificados diversos arquivos de workflow no diretório `.github/workflows/`. Esses arquivos definem ações automatizadas executadas durante o ciclo de desenvolvimento do projeto.

Complementarmente, foi realizada uma análise do histórico de commits. Essa verificação permitiu identificar o primeiro commit diretamente relacionado à criação e evolução dos workflows de CI. Destaca-se o commit **6d336c1**, no qual foi adicionada uma pipeline de GitHub Actions voltada para:

- Execução de *linting* para verificação da qualidade e padronização do código;
- Execução de testes automatizados;
- Suporte a múltiplas versões do Python (3.10 e 3.11);
- Introdução da ferramenta **tox** para gerenciamento de ambientes de teste.

Além disso, a aba **Actions** do GitHub apresenta um histórico consistente de execuções dos workflows, indicando que os pipelines estão ativos e em uso contínuo.

No histórico de **Pull Requests**, é possível observar a presença de *status checks* visuais (❌ falha ou ✅ sucesso), que informam aos revisores se as verificações automatizadas foram concluídas com êxito antes da integração do código ao branch principal.

Essas evidências confirmam que o projeto possui automação funcional e integrada ao processo de colaboração.

---

## 6. Fluxo Atual

Com base na análise realizada, o fluxo atual de desenvolvimento do projeto pode ser descrito da seguinte forma:

1. **Criação de alterações no código-fonte**  
   Os contribuidores realizam modificações localmente e submetem essas alterações ao repositório por meio de commits.

2. **Abertura de Pull Requests (PRs)**  
   As mudanças são integradas ao fluxo principal através da abertura de Pull Requests, permitindo revisão por outros colaboradores ou mantenedores.

3. **Execução automática dos workflows de CI**  
   Ao ocorrer um evento de *push* ou a abertura/atualização de um Pull Request, os workflows definidos em `.github/workflows/` são acionados automaticamente pelo GitHub Actions.  
   As etapas incluem:
   - Instalação de dependências;
   - Execução de ferramentas de linting;
   - Execução de testes automatizados em múltiplas versões do Python, utilizando **tox**.

4. **Feedback automatizado**  
   Os resultados das execuções são exibidos diretamente no Pull Request por meio de *status checks*, fornecendo feedback imediato sobre a qualidade e integridade do código.

5. **Revisão e integração do código**  
   Após a conclusão bem-sucedida das verificações automatizadas, o Pull Request pode ser revisado e, se aprovado, mesclado ao branch principal.

Esse fluxo reduz a dependência de validações manuais, minimiza riscos de regressão e padroniza o processo de contribuição.

---

## 7. Conclusão

A análise do projeto LangExtract demonstra um nível consistente de maturidade no uso de práticas de Integração Contínua. A adoção do GitHub Actions, aliada à execução automatizada de linting e testes em múltiplas versões do Python, contribui diretamente para a manutenção da qualidade do código e para a detecção precoce de erros.

A integração dos pipelines ao fluxo de Pull Requests evidencia uma preocupação com a estabilidade do projeto e com a prevenção de regressões, aspectos fundamentais para a evolução sustentável do software. Além disso, o feedback automatizado facilita a entrada de novos contribuidores, ao estabelecer critérios claros e objetivos para a aceitação de mudanças.

Dessa forma, conclui-se que o LangExtract possui um processo de desenvolvimento bem estruturado no que se refere à Integração Contínua, reduzindo gargalos manuais e fortalecendo a confiabilidade do projeto ao longo de seu ciclo de vida.
