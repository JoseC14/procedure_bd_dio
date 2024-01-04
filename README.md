## PARTE 1
#  Qual o departamento com maior número de pessoas?
  `SELECT * FROM department WHERE employers IN(SELECT MAX(employers) FROM DEPARTMENT)`
# Quais são os departamentos por cidade
  `SELECT address, COUNT(section) FROM deparment GROUP BY address`
# Relação de empregados por departamento
  `SELECT * FROM department`

# Porque criei o Indíce em employers?
por conta da query de departamento por Cidade
`CREATE INDEX idx_mr_ppl ON department(employers)`

## PARTE 2

# Query de Procedure para Ecommerce

`CREATE PROCEDURE exec_query_cliente (IN operation INT,IN Nome VARCHAR(150),IN Identificacao VARCHAR(50),IN Endereco VARCHAR(50),IN Id INT)`
`BEGIN`
	 `IF id = NULL THEN SET Id = 0; END IF;`
     
	 IF operation = 1 THEN
		INSERT INTO cliente(nome,identificacao,endereco) VALUES(Nome,Identificacao,Endereco);
     ELSEIF operation = 2 THEN 
		UPDATE cliente SET nome = Nome, identificacao = Identificao, endereeco = Endereco WHERE id = Id;
	 ELSEIF operation = 3 THEN 
		DELETE FROM cliete WHERE id = Id;
    END IF;
`END;`

# Query de Procedure para Universidade 

`PROCEDURE qry_student (IN operation INT, IN FirstName VARCHAR(100), IN LastName VARCHAR(100), IN NumRegistration INT, IN Id_Major INT, IN Id_Class INT, IN Id INT)
BEGIN
	IF operation = 1 THEN
		INSERT INTO student(firstName,lastName,numRegistration,id_major,id_class) VALUES(FirstName,LastName,NumRegistration,Id_Major,Id_Class);
	ELSEIF operation = 2 THEN
		UPDATE student SET firstName = FirstName, lastName = LastName, numRegistration = NumResgistration, id_major = Id_Major, id_class = Id_Class WHERE id = Id;
	ELSEIF operation = 3 THEN
		DELETE FROM student where id = Id;
	END IF ;
END`
