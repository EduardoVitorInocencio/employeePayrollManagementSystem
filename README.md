### Employee Payroll Management Database in MySQL

![image](https://github.com/EduardoVitorInocencio/employeePayrollManagementSystem/assets/136349773/6dc8e018-b25e-4a57-9300-fdca7de25d3a)

#### 1. Informações do Funcionário
   
   Os dados dos funcionários são muito essenciais para manter um registro adequado dos funcionários e de seus dados pessoais.
   informações para diversos fins, como contatá-los para convidá-los para determinada cúpula, feedback do
   empresa a partir dos dados dos funcionários

#### 2. Manutenção do salário

   É muito importante manter esses dados que ajudarão não só os gestores e o RH a acompanhar o
   salários dos funcionários, mas também ajudam a empresa ou seu conselho a analisar quanto estão gastando em um
   determinado funcionário de uma determinada empresa

#### 4. Local de trabalho
   É muito importante para uma organização pequena ou grande ter um registro de todos os locais de trabalho onde trabalham.
   operar para ver como eles podem se desenvolver naquela região específica e também aumentar as contratações naquela região
   para que a organização possa aumentar o alcance do mercado naquela área.

#### 6. Projetos
   Para ter sucesso a empresa deve estar envolvida em vários projetos, por isso também precisa manter o
   registro dos salários que cada funcionário está recebendo por um tipo específico de projeto em que está trabalhando


### -------------------------------------------- _Lista de Entidade do Banco_  ------------------------------------------------

### Employee
A tabela de funcionários incluirá todos os dados pessoais do funcionário e será uma cobertura geral
informações desse funcionário específico.

Campos da tabela:

- Employee_Id: Este campo armazena o identificador único de cada funcionário. É do tipo NUMBER com uma precisão de 6 dígitos.

- First_Name: Este campo armazena o primeiro nome do funcionário. É do tipo VARCHAR2 com um comprimento máximo de 25 caracteres.

- Last_Name: Este campo armazena o sobrenome do funcionário. Também é do tipo VARCHAR2 com um comprimento máximo de 25 caracteres.

- Hire_Date: Este campo registra a data de contratação do funcionário. É do tipo DATE.

- City: Este campo armazena a cidade onde o funcionário está localizado. É do tipo VARCHAR2 com um comprimento máximo de 25 caracteres.

- State: Este campo armazena o estado onde o funcionário está localizado. Também é do tipo VARCHAR2 com um comprimento máximo de 25 caracteres
