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


### --------------------------------------- _Lista de Entidade do Banco_  ------------------------------------------------

### Table Employee
A tabela de funcionários incluirá todos os dados pessoais do funcionário e será uma cobertura geral
informações desse funcionário específico.

Campos da tabela:

- Employee_Id: Este campo armazena o identificador único de cada funcionário. É do tipo NUMBER com uma precisão de 6 dígitos.

- First_Name: Este campo armazena o primeiro nome do funcionário. É do tipo VARCHAR2 com um comprimento máximo de 25 caracteres.

- Last_Name: Este campo armazena o sobrenome do funcionário. Também é do tipo VARCHAR2 com um comprimento máximo de 25 caracteres.

- Hire_Date: Este campo registra a data de contratação do funcionário. É do tipo DATE.

- City: Este campo armazena a cidade onde o funcionário está localizado. É do tipo VARCHAR2 com um comprimento máximo de 25 caracteres.

- State: Este campo armazena o estado onde o funcionário está localizado. Também é do tipo VARCHAR2 com um comprimento máximo de 25 caracteres

### Table Salary

A Tabela Salarial cobrirá todos os salários atuais e anteriores que um funcionário teve ou tem atualmente. Esta tabela irá
ajudar um gerente/RH a analisar qual funcionário foi promovido em que data ou quando foi
faixa salarial alterada.

Campos da tabela:

- Salary_Id: Este campo armazena o identificador único de cada registro de salário. É do tipo NUMBER.

- Gross_Salary: Este campo armazena o salário bruto do funcionário. É do tipo NUMBER.

- Hourly_Pay: Este campo armazena o pagamento por hora do funcionário, se aplicável. É do tipo NUMBER.

- State_Tax: Este campo armazena o valor do imposto estadual retido do salário do funcionário. É do tipo NUMBER.

- Federal_Tax: Este campo armazena o valor do imposto federal retido do salário do funcionário. É do tipo NUMBER.

- Account_Id: Este campo armazena o identificador da conta associada ao salário do funcionário. É uma chave estrangeira (FOREIGN KEY) que faz referência à tabela ACCOUNTDETAILS, onde o Account_Id é a chave primária.

Além disso, há uma restrição definida na tabela:

- `SALARY_PK:` Esta é uma restrição de chave primária (PRIMARY KEY) que garante que o campo Salary_Id seja único para cada registro na tabela Salary.


### Table Departament

A Tabela de Departamentos mantém os dados de todos os departamentos possíveis aos quais um funcionário pode pertencer.

Campos da tabela:

- Department_Id: Este campo armazena o identificador único de cada departamento. É do tipo NUMBER e pode conter valores inteiros. Este campo é definido como NOT NULL, o que significa que é obrigatório fornecer um valor para cada registro na tabela.

- Department_Name: Este campo armazena o nome do departamento. É do tipo VARCHAR2 com um comprimento máximo de 30 caracteres. Este campo também é definido como NOT NULL, garantindo que cada departamento tenha um nome associado.

Além disso, há uma restrição definida na tabela:

- `DEPARTMENT_PK:` Esta é uma restrição de chave primária (PRIMARY KEY) que garante que o campo Department_Id seja único para cada registro na tabela. Isso impede a duplicação de identificadores de departamento, garantindo a integridade dos dados.


### Table DepartmentProject Bridge

A tabela DepartmentProject é uma tabela de associação entre os departamentos e os projetos, muitas vezes usada em esquemas de banco de dados relacionais para representar a relação de muitos-para-muitos entre entidades. Aqui está a descrição dos campos:

 - Department_Id: Este campo armazena o identificador do departamento. É do tipo NUMBER.

- Project_Id: Este campo armazena o identificador do projeto. Também é do tipo NUMBER.

Essa tabela não possui campos adicionais além das chaves estrangeiras que referenciam as tabelas Department e Project. As chaves estrangeiras garantem a integridade referencial, ou seja, garantem que os valores armazenados nos campos Department_Id e Project_Id existam nas respectivas tabelas Department e Project.

Além disso, a tabela possui uma chave primária composta, que consiste nos campos Department_Id e Project_Id, definida pela restrição DEPTPROJECT_PK. Isso garante que cada combinação de departamento e projeto seja única na tabela DepartmentProject.

Essa estrutura permite associar múltiplos projetos a múltiplos departamentos, refletindo uma relação de muitos-para-muitos entre departamentos e projetos.

