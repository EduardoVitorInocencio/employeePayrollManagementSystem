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

A tabela DepartmentProject é uma tabela de associação entre os departamentos e os projetos, muitas vezes usada em esquemas de banco de dados relacionais para representar a relação de muitos-para-muitos entre entidades.

Campos da tabela:

 - Department_Id: Este campo armazena o identificador do departamento. É do tipo NUMBER.

- Project_Id: Este campo armazena o identificador do projeto. Também é do tipo NUMBER.

Essa tabela não possui campos adicionais além das chaves estrangeiras que referenciam as tabelas Department e Project. As chaves estrangeiras garantem a integridade referencial, ou seja, garantem que os valores armazenados nos campos Department_Id e Project_Id existam nas respectivas tabelas Department e Project.

Além disso, a tabela possui uma chave primária composta, que consiste nos campos Department_Id e Project_Id, definida pela restrição DEPTPROJECT_PK. Isso garante que cada combinação de departamento e projeto seja única na tabela DepartmentProject.

Essa estrutura permite associar múltiplos projetos a múltiplos departamentos, refletindo uma relação de muitos-para-muitos entre departamentos e projetos.

### Table Project

Esta tabela inclui os dados de todos os projetos em que uma determinada empresa está trabalhando ou os projetos nos quais
a empresa vai funcionar no futuro.

Campos da tabela:

- Project_Id: Este campo armazena o identificador único de cada projeto. É do tipo NUMBER, o que sugere que é uma identificação numérica. No entanto, não há especificação de precisão, então assumiremos que é uma numeração inteira. Este campo é definido como a chave primária (PRIMARY KEY) da tabela, o que garante que cada identificador de projeto seja único.

- Project_Name: Este campo armazena o nome do projeto. É do tipo VARCHAR2 com um comprimento máximo de 50 caracteres. Parece ser uma descrição concisa do nome do projeto.

- Project_Description: Este campo armazena uma breve descrição do projeto. É do tipo VARCHAR2 com um comprimento máximo de 50 caracteres. Provavelmente é uma descrição curta que fornece informações adicionais sobre o projeto.

Esses campos fornecem informações básicas sobre os projetos e são úteis para identificar, descrever e distinguir os diferentes projetos dentro de um sistema ou banco de dados.


### Table Account Details 

A Tabela de Detalhes da Conta manterá os dados relativos às contas às quais o funcionário se conectou
a empresa para que seu salário seja creditado.

Campos da tabela:

- Account_Id: Este campo armazena o identificador único da conta. É do tipo NUMBER.

- Bank_Name: Este campo armazena o nome do banco associado à conta. É do tipo VARCHAR2 com um comprimento máximo de 50 caracteres.

- Account_Number: Este campo armazena o número da conta. É do tipo VARCHAR2 com um comprimento máximo de 50 caracteres.

- Employee_Id: Este campo armazena o identificador do funcionário associado à conta. É do tipo NUMBER e é uma chave estrangeira (FOREIGN KEY) que faz referência ao campo Employee_Id na tabela Employee, conectando as informações da conta ao funcionário correspondente.

A tabela também possui as seguintes restrições:

- Account_PK: Esta é uma restrição de chave primária (PRIMARY KEY) que garante que o campo Account_Id seja único para cada registro na tabela AccountDetails. Isso impede a duplicação de identificadores de conta.

- FOREIGN KEY (Employee_Id) REFERENCES Employee(Employee_Id): Esta é uma restrição de chave estrangeira que estabelece uma relação entre o campo Employee_Id na tabela AccountDetails e o campo Employee_Id na tabela Employee. Isso garante que cada Employee_Id na tabela AccountDetails corresponda a um Employee_Id existente na tabela Employee, mantendo a integridade referencial entre as tabelas.


### Table Education

A Tabela de Educação acompanha a escolaridade do funcionário incluindo seus diplomas alcançados até
agora.

Campos da tabela:

- Education_Id: Este campo armazena o identificador único de cada registro de educação. É do tipo NUMBER.

- Employee_Id: Este campo armazena o identificador único do funcionário associado a essa entrada de educação. É do tipo NUMBER e serve como uma chave estrangeira (FOREIGN KEY) referenciando o campo Employee_Id na tabela Employee.

- Degree: Este campo armazena o grau ou diploma obtido pelo funcionário. É do tipo VARCHAR com um comprimento máximo de 30 caracteres.

- Graduation_Year: Este campo armazena o ano de graduação do funcionário. É do tipo NUMBER com uma precisão de 4 dígitos.

A tabela Education parece estar relacionada à educação dos funcionários, armazenando informações como grau obtido e ano de graduação. Além disso, há uma restrição definida na tabela:

- Location_PK: Esta é uma restrição de chave primária (PRIMARY KEY) que garante que o campo Education_Id seja único para cada registro na tabela. Isso impede a duplicação de identificadores de educação.

### Table Leave

A tabela de licenças mantém o registro do número de licenças que um funcionário tira ou tirou ao longo de
qualquer mês ou um ano.

Campos da tabela:

- Leave_Id: Este campo armazena o identificador único de cada pedido de licença. É do tipo NUMBER.

- Employee_Id: Este campo armazena o identificador único do funcionário associado ao pedido de licença. É do tipo NUMBER e é uma chave estrangeira (FOREIGN KEY) que faz referência ao campo Employee_Id da tabela Employee, relacionando os pedidos de licença aos funcionários correspondentes.

- Leave_date: Este campo registra a data em que o pedido de licença foi feito. É do tipo DATE.

Além disso, existem as seguintes restrições definidas na tabela:

- Leave_PK: Esta é uma restrição de chave primária (PRIMARY KEY) que garante que o campo Leave_Id seja único para cada registro na tabela, impedindo a duplicação de identificadores de pedidos de licença.

- FOREIGN KEY (Employee_Id) REFERENCES Employee(Employee_Id): Esta é uma restrição de chave estrangeira que garante que o valor presente no campo Employee_Id na tabela Leave corresponda a um valor existente no campo Employee_Id na tabela Employee, garantindo a integridade referencial entre as duas tabelas. Isso significa que cada pedido de licença está associado a um funcionário existente na tabela de funcionários.

### Table  EmployeeAttendance Bridge

A tabela Employee_Attendance tem como objetivo armazenar informações sobre a presença dos funcionários em determinados momentos, permitindo o acompanhamento da frequência de cada funcionário ao trabalho.

Campos da tabela:

- Employee_Id: Este campo armazena o identificador único do funcionário associado à presença. É do tipo NUMBER e é usado como uma chave estrangeira (FOREIGN KEY) referenciando a tabela Employee, especificamente o campo Employee_Id.

- Attendance_Id: Este campo armazena o identificador único da presença. É do tipo NUMBER e é usado como uma chave estrangeira (FOREIGN KEY) referenciando a tabela Attendance, especificamente o campo Attendance_Id.

Além disso, há uma restrição definida na tabela:

- DEPARTMENTPROJECT_PK: Esta é uma restrição de chave primária (PRIMARY KEY) que combina os campos Employee_Id e Attendance_Id, garantindo que cada par de valores seja único na tabela Employee_Attendance. Essa restrição impede a duplicação de entradas de presença para um mesmo funcionário em um mesmo dia.
As chaves estrangeiras (FOREIGN KEY) garantem que os valores nos campos Employee_Id e Attendance_Id estejam presentes nas tabelas Employee e Attendance, respectivamente, garantindo a integridade referencial entre as tabelas.

### Table Attendence

A tabela Attendance será utilizada para registrar a frequência e a quantidade de horas trabalhadas do funcionários.

Campos da tabela:

- Attendance_Id: Este campo representa o identificador único de cada registro de comparecimento. É do tipo NUMBER e não parece ser uma sequência automática, pois não está especificado como IDENTITY ou AUTOINCREMENT. Portanto, provavelmente é necessário fornecer valores manualmente para este campo.

- Hours_Worked: Este campo armazena o número de horas trabalhadas durante o comparecimento registrado. É do tipo NUMBER e parece armazenar valores numéricos representando as horas trabalhadas.

Além disso, há uma restrição definida na tabela:

- Attendance_PK: Esta é uma restrição de chave primária (PRIMARY KEY) que garante que o campo Attendance_Id seja único para cada registro na tabela, evitando duplicações de IDs de frequência.

### Table Work Location

O nome da tabela diz a maioria das coisas. Esta tabela inclui a localização do escritório, qual cidade está
está localizado, em que estado está e também rastreia o número de funcionários em um determinado local.

Campos da tabela:

- Location_Id: Este campo armazena o identificador único de cada local de trabalho. É do tipo NUMBER e é definido como a chave primária (PRIMARY KEY) da tabela, garantindo que cada local de trabalho tenha um identificador exclusivo.

- Location: Este campo armazena o nome ou descrição do local de trabalho. É do tipo VARCHAR2 com um comprimento máximo de 25 caracteres.

- Number_Of_Employees: Este campo armazena o número de funcionários que trabalham neste local. É do tipo NUMBER.

- City: Este campo armazena a cidade onde o local de trabalho está localizado. É do tipo VARCHAR2 com um comprimento máximo de 25 caracteres.

- State: Este campo armazena o estado onde o local de trabalho está localizado. Também é do tipo VARCHAR2 com um comprimento máximo de 25 caracteres.

Esses campos fornecem informações essenciais sobre os locais de trabalho, como sua localização, número de funcionários e outras informações relevantes. A chave primária garante a unicidade dos registros na tabela.

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Consultas em SQL (Queries)

1. Selecione todos os funcionários e seus respectivos salários brutos;
2. Obtenha o nome e a descrição de todos os projetos;
3. Encontre todos os departamentos e o número de funcionários em cada departamento;
4. Selecione o nome do banco e o número da conta bancária de todos os funcionários;
5. Encontre o número de horas trabalhadas por cada funcionário;
6. Obtenha todos os funcionários que se formaram em um ano anterior a 2010 e sua respectiva graduação;
7. Encontre todos os funcionários que têm uma conta bancária e um salário associado;
8. Selecione todos os funcionários que têm férias marcadas para depois de 2023;
9. Encontre o número total de funcionários em cada cidade de trabalho;
10. Obtenha o salário bruto médio de todos os funcionários;



