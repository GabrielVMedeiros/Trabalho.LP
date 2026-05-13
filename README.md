# Projeto: UnB no Ponto

1. Estrutura de Banco de Dados (Requisitos de BD) 
Para atingir as 10 entidades obrigatórias e as funcionalidades avançadas, não foque
apenas na linha de ônibus, mas em todo o ecossistema de transporte do campus.

• Entidades Sugeridas:
o Usuario (Estudante/Servidor)
o Linha (Ex: 0.110, 110.2)
o PontoDeParada (Localização física no campus ou arredores)
o Horario (Tabela de horários de cada linha)
o Empresa (Operadora do ônibus)
o Veiculo (Informações sobre o ônibus, ex: tem acessibilidade?)
o Favorito (Relação entre usuário e suas linhas frequentes)
o Ocorrencia (Relatos de atraso ou lotação feitos pelos usuários)
o Campus (Darcy Ribeiro, Ceilândia, Gama, Planaltina)
o Anexo (Campo Binário para PDF do itinerário oficial ou foto do ponto).
• Lógica Avançada no SQL:
o View: Criar uma visão que mostre "Próximos Ônibus" cruzando as
tabelas de Linha, Ponto e Horario.
o Trigger: Sempre que um usuário cadastrar uma Ocorrencia de "Atraso",
um gatilho pode atualizar o status daquela Linha para "Operando com
Atraso".

2. Implementação em Go (Requisitos de LP)
   
Aqui você demonstra o domínio da linguagem para o Professor Marcelo Ladeira.

• Abstração e Encapsulamento: Utilize Interfaces em Go para definir como o
sistema busca a localização. Você pode ter uma interface Localizador e
implementações diferentes (uma que usa GPS real e outra que simula
coordenadas para testes).
• Tratamento de Erros: Use o padrão de retorno de erros do Go para lidar com
falhas de conexão ao banco de dados, o que é um ótimo ponto para o vídeo de
análise da linguagem.
• Concorrência: Se o sistema precisar consultar APIs externas (como a do
DFTrans), você pode usar Goroutines para buscar dados de múltiplas linhas
simultaneamente, tornando a resposta mais rápida.

3. A Funcionalidade de Localização
   
Como o projeto de BD pede uma interface gráfica para usuários leigos, você pode:

1. Ter um mapa simples (usando uma biblioteca como Leaflet no navegador) onde
o usuário clica onde está.
2. O backend em Go recebe essa coordenada e faz uma busca no banco de dados
(usando fórmulas de distância ou funções espaciais se o SGBD permitir) para
retornar os pontos de parada num raio de X metros.

1. Divisão de Papéis (Equipe de 5)
   
• Integrante 1 – Todo mundo menos o Gabriel (Líder de Dados): Responsável
pelo Modelo ER, Relacional e Scripts SQL (Triggers/Procedures).

• Integrante 2- Erick e Gabriel (Desenvolvedor Backend): Responsável pela API
em Go, structs e lógica de geolocalização.

• Integrante 3- Cecília (Desenvolvedor Frontend): Responsável pela interface
gráfica para o usuário leigo e integração com o CRUD.

• Integrante 4- Gabriel e Erick (Analista de LP): Responsável pela Wiki, análise
dos critérios de Sebesta e documentação técnica.

• Integrante 5- Carol (Media & QA): Responsável pelo roteiro e edição do vídeo
de 10 min, inserção de dados binários e testes de integridade.

2. Cronograma de Atividades (Maio - Julho 2026)

Fase 1: Definição e Modelagem (05/05 a 20/05)

Foco: Cumprir o primeiro prazo de BD e preparar o 1º Seminário de LP.
• 05/05 (Hoje): Enviar nomes do grupo e o tema "UnB no Ponto" para o professor
de BD.
• 10/05: Integrante 1 finaliza o Diagrama de Entidade-Relacionamento (10
entidades).
• 15/05: Integrante 2 inicia o esqueleto do projeto em Go (configuração do
ambiente e conexão DB).
• 20/05: Apresentação do 1º Seminário de LP. O grupo deve mostrar a análise
inicial da linguagem e o andamento do projeto.

Fase 2: Implementação da Primeira Parte (21/05 a 30/05)

Foco: Entrega da Parte 1 de BD.

• 25/05: Integrante 1 finaliza o Script SQL e o Modelo Relacional.
• 27/05: Integrante 4 e 5 preparam o PDF da primeira entrega de BD.
• 30/05: DATA LIMITE: Entrega da 1ª Parte de BD (Introdução, MER, MR, Script
SQL e IA).

Fase 3: Desenvolvimento do CRUD e Lógica (01/06 a 20/06)

Foco: Funcionalidades avançadas e vídeo de LP.

• 05/06: Integrante 2 e 3 finalizam o CRUD funcional (Create, Read, Update,
Delete) em Go.
• 10/06: Apresentação do 2º Seminário de LP. Focar em encapsulamento e
abstração do código.
• 15/06: Integrante 1 e 2 implementam a Procedure e o Trigger (ex: alerta de
atraso) no banco.
• 20/06: Integrante 5 grava as demonstrações do sistema para o vídeo de LP.

Fase 4: Finalização e Defesa (21/06 a 15/07)

Foco: Entrega final e apresentações.

• 26/06: Integrante 5 finaliza a Wiki do projeto com a descrição das atividades de
cada membro.
• 30/06 a 02/07: Apresentação Final de BD. Todos devem estar presentes para
defender o projeto funcionando.
• 08/07: DATA LIMITE (LP): Enviar o vídeo de 10 min e o link da Wiki/Github.
• 10/07 a 15/07: Seminários finais de apresentação de LP.

4. Checklist de Requisitos Críticos (Não esqueçam!)
   
• Dado Binário: Integrante 5 deve garantir que o sistema armazene pelo menos
um PDF (itinerário) ou Foto (ponto de ônibus) no banco.
• Critérios de LP: O Integrante 4 deve garantir que o vídeo cite os critérios de
avaliação (legibilidade, confiabilidade, etc.) conforme o livro do Sebesta.
• Uso de IA: Todas as entregas devem indicar onde e como ferramentas de IA
foram utilizadas.
Dica de Integração: Usem o mesmo repositório no GitHub para ambas as matérias,
mas criem pastas separadas para a documentação específica de cada uma (ex:
/docs/BD e /docs/LP). Isso facilita a gestão dos Integrantes 4 e 5.
