/* create database iftm;
drop database iftm;
create table tb1
(
cpf int not null,
nome varchar(50) not null,
rg varchar(11) not null,
primary key (cpf)
);
create table tb2
(
id int not null auto_increment,
nome varchar(50) not null,
cpf int(11) not null,
valor numeric(3,2),
primary key(id),
constraint fk1 foreign key(cpf) references tb1(cpf)
);
alter table tb1 add column nota numeric(2,1) not null;
alter table tb1 change nota media numeric(2,1) not null;
*/
create database Atividade1;
create table Pessoa(

cpf int(11)  not null,
nome varchar(45) not null,
Idade int not null,
Sexo varchar(1),
primary key (cpf)

);

create table Funcionario(

idFuncionario int not null auto_increment,
Pessoa_cpf int(11)  not null,
primary key (idFuncionario),
constraint fk_funcionario_pessoa foreign key(Pessoa_cpf) references Pessoa(cpf)

);


create table Professor(

idProfessor int not null auto_increment,
Professor_cpf int(11)  not null,
Disciplina_idDisciplina int not null,
primary key (idProfessor),
constraint fk_professor_pessoa foreign key(Professor_cpf) references Pessoa(cpf)
);

create table Disciplina(
idDisciplina int not null auto_increment,
Nome varchar(45) not null,
Semestre int not null,
CargaHoraria varchar(45) not null,
primary key (idDisciplina)
);

alter table Professor add constraint fk1_professor_disciplina foreign key(Disciplina_idDisciplina) references Disciplina(idDisciplina);



create table Aluno(
idAluno int not null auto_increment,
Pessoa_cpf int(11) not null,
primary key(idAluno),
constraint fk_aluno_Pessoa foreign key(Pessoa_cpf) references Pessoa(cpf)

); 
