# SQL_FILMES
CREATE TABLE ENTRETERIMENTO (ID INT AUTO_INCREMENT PRIMARY KEY, NOME VARCHAR(100) NOT NULL, TIPO ENUM('FILME', 'SÉRIE') NOT NULL, DIRETOR VARCHAR(100), ATOR_PRINCIPAL VARCHAR(100), ATRIZ_PRINCIPAL VARCHAR(100), ANO_LANCAMENTO INT, DURACAO_MINUTOS INT, CLASSIFICACAO_ETARIA VARCHAR(5), GENERO VARCHAR(50) );

01. Crie um script SQL que mostre todas as colunas, onde liste apenas o TIPO "série" da tabela de ENTRETERIMENTO:
   
SELECT * FROM ENTRETERIMENTO WHERE TIPO = 'SÉRIE';

3. Crie um script SQL que mostre todas as colunas, onde liste apenas o TIPO "série" da tabela de ENTRETERIMENTO, mas em ordem alfabética de NOMES(de A até Z):
   
SELECT * FROM ENTRETERIMENTO WHERE TIPO = 'SÉRIE' ORDER BY NOME;

5. Crie um script SQL que mostre apenas o TIPO "série" da tabela de ENTRETERIMENTO, porém de forma alfabética INVERTIDA (de Z para A):
   
SELECT * FROM ENTRETERIMENTO WHERE TIPO = 'SÉRIE' ORDER BY NOME DESC;

7. Crie um script SQL que mostre apenas o TIPO "FILME" da tabela de ENTRETERIMENTO:
   
SELECT * FROM ENTRETERIMENTO WHERE TIPO = 'FILME';

9. Liste os filmes que foram produzidos antes dos anos 2000:

SELECT * FROM ENTRETERIMENTO WHERE TIPO = 'FILME' AND ANO_LANCAMENTO < 2000;

11. Liste as séries que foram produzidas após o ano 2015:
    
SELECT * FROM ENTRETERIMENTO WHERE TIPO = 'SÉRIE' AND ANO_LANCAMENTO > 2015;

13. Liste os filmes de ação(e suas variações, como por exemplo: Ação/Drama);
    
SELECT * FROM ENTRETERIMENTO WHERE TIPO = 'FILME' AND GENERO LIKE '%Drama%';

15. Mostre os filmes que tem duração superior a 2horas;
    
SELECT * FROM ENTRETERIMENTO WHERE DURACAO_MINUTOS > 120;

17. Liste as séries que foram produzidas entre os anos de 2012 até 2016, em ordem de ano e em seguida pelo nome da série;
    
SELECT * FROM ENTRETERIMENTO WHERE ANO_LANCAMENTO > 2012 AND ANO_LANCAMENTO < 2016 ORDER BY ANO_LANCAMENTO, NOME;

19. Mostre os filmes que o ator Brad Pitt trabalhou por onde do filme mais antigo para o mais novo;
    
SELECT * FROM ENTRETERIMENTO WHERE TIPO = 'FILME' AND ATOR_PRINCIPAL = 'Brad Pitt' ORDER BY ANO_LANCAMENTO;

21. Liste apenas o campo NOME, DIRETOR, ATOR PRINCIAL dos itens que são do gênero "crime" (e suas variações) e o ator seja "John Travolta";
    
SELECT NOME, DIRETOR, ATOR_PRINCIPAL FROM ENTRETERIMENTO WHERE GENERO LIKE '%Crime%' AND ATOR_PRINCIPAL = 'John Travolta';

23. Liste os itens que a duração seja superior a 2 horas e que o ator NÃO seja Christian Bale ou Tim Robbins
    
SELECT * FROM ENTRETERIMENTO WHERE DURACAO_MINUTOS > 120 AND ATOR_PRINCIPAL NOT IN ('Christian Bale', 'Tim Robbins');

25. Liste os itens que NÃO seja de Comédia ou drama;
    
SELECT * FROM ENTRETERIMENTO WHERE GENERO NOT LIKE '%Comédia%' AND GENERO NOT LIKE '%Drama%';

27. Liste todos os itens que foram criados, que não seja dos anos 2000, 2001 ou 2002;
    
SELECT * FROM ENTRETERIMENTO WHERE ANO_LANCAMENTO NOT IN (2000, 2001, 2002);

29. Liste os itens que tiveram como ator Wagner Moura ou Leonardo DiCaprio ou Keanu Reeves
    
SELECT * FROM ENTRETERIMENTO WHERE ATOR_PRINCIPAL IN ('Wagner Moura', 'Leonardo DiCaprio', 'Keanu Reeves');
