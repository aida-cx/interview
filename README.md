# Análise de Ligações Relacionadas a Reclamações

## Contexto
Uma empresa de atendimento ao cliente via call center possui dois principais sistemas:

### 1. CRM
Utilizado pelos atendentes para registrar os atendimentos. Os dados relevantes deste sistema estão no arquivo `crm.csv`, contendo:

- **ID_ASSISTENCIA:** Número único de protocolo.
- **DATAABERTURA:** Data de abertura do protocolo (pode ser alterada quando um novo serviço é adicionado ao protocolo).
- **NUMEROSERVICO:** Número do serviço (1 representa a abertura do serviço, os demais são adicionais).
- **DATACADASTRO:** Momento em que o atendente registrou a informação no sistema.

### 2. Telefonia
Contém os dados de todas as ligações recebidas e realizadas pela empresa. As informações relevantes estão no arquivo `calls.csv`:

- **recording_id:** Nome do arquivo de áudio (gravação).
- **pbx_login_id:** ID do agente que atendeu a ligação.
- **parentinum:** Identificador da chamada (considerar gravações com chamadas únicas).
- **datetime:** Momento da ligação.
- **duration:** Duração da ligação.
- **direction:** Indica se a ligação foi recebida ou feita.

### 3. Reclamações
Registro das reclamações feitas pelos clientes, contidas no arquivo `complaint.csv`, com as seguintes informações importantes:

- **ID_ASSISTENCIA:** Número único de protocolo da reclamação.
- **DATACADASTRO:** Momento em que a reclamação foi registrada.

## Objetivo da Prova
O candidato deverá analisar todas as ligações que tiveram relação com uma reclamação. Para isso, deve:

1. Identificar todas as reclamações registradas no arquivo `complaint.csv` e listar os **ID_ASSISTENCIA** envolvidos.
    - Neste caso iremos somente analisar reclamações relatadas no ano de 2025 e que foram iniciadas tambem no ano de 2025
2. Para cada **ID_ASSISTENCIA** presente no arquivo de reclamações, buscar todas as interações correspondentes no CRM (`crm.csv`).
3. A partir dessas interações, encontrar as ligações relacionadas no arquivo `calls.csv`, considerando datas e possíveis agentes envolvidos.
4. Gerar um arquivo final `resultado.csv` contendo as informações consolidadas das ligações associadas às reclamações.
    - Preciso das informações contidadas `calls.csv` junto com o **ID_ASSISTENCIA** correspondente a ele.

## Ponto de atenção

1. As datas e horarios não são precisos, portanto, é necessário considerar uma margem de erro ao analisar as interações.
2. Nem toda interação do CRM teve uma ligação correspondente.

## Critérios de Avaliação

- Correta extração e vinculação dos dados entre os três arquivos.
- Precisão na identificação das ligações relacionadas.
- Estrutura e clareza do código desenvolvido.
- Uso adequado de bibliotecas de análise de dados, como Pandas (caso utilize Python).
- Apresentação correta do arquivo final `resultado.csv` com todas as informações relevantes.

## Entrega
O candidato deverá enviar:

- O código-fonte desenvolvido para realizar a análise.
- O arquivo `resultado.csv` gerado.
- Um breve resumo explicando a abordagem utilizada.