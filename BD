create database med_org;
use med_org;

create table patient (
    patient_id INT(3) PRIMARY KEY AUTO_INCREMENT,
    patient_name VARCHAR(30),
    patient_telephone VARCHAR(12),
    patient_sex VARCHAR(2),
    patient_age INT(3));  
    
create table doctor (
    doctor_id INT(3) PRIMARY KEY AUTO_INCREMENT,
    doctor_name VARCHAR(30),
    doctor_telephone VARCHAR(12),
    doctor_sex VARCHAR(2),
    doctor_age INT(3),
    doctor_experience INT(2),
    doctor_job VARCHAR(20),
    doctor_room INT(3));      
        
create table pat_in_dep (
    pat_in_dep_id INT(3) PRIMARY KEY AUTO_INCREMENT,
    patient_id INT(3),
    department_id INT(3),
    FOREIGN KEY (patient_id) REFERENCES patient (patient_id) on delete set null); 
    
create table pat_in_fil (
    pat_in_fil_id INT(3) PRIMARY KEY AUTO_INCREMENT,
    patient_id INT(3),
    filial_id INT(3),
    FOREIGN KEY (patient_id) REFERENCES patient (patient_id) on delete set null); 
    
create table doc_in_dep (
    doc_in_dep_id INT(3) PRIMARY KEY AUTO_INCREMENT,
    doctor_id INT(3),
    department_id INT(3),
    FOREIGN KEY (doctor_id) REFERENCES doctor (doctor_id) on delete set null); 
    
create table doc_in_fil (
    doc_in_fil_id INT(3) PRIMARY KEY AUTO_INCREMENT,
    doctor_id INT(3),
    filial_id INT(3),
    FOREIGN KEY (doctor_id) REFERENCES doctor (doctor_id) on delete set null);     
    
create table department (
    dep_id INT(3) PRIMARY KEY AUTO_INCREMENT,
    department_id INT(3),
    pat_in_dep_id INT(3),
    doc_in_dep_id INT(3),
    department_name VARCHAR(20),
    FOREIGN KEY (pat_in_dep_id) REFERENCES pat_in_dep (pat_in_dep_id) on delete set null,
    FOREIGN KEY (doc_in_dep_id) REFERENCES doc_in_dep (doc_in_dep_id) on delete set null);

create table filial (
    fil_id INT(3) PRIMARY KEY AUTO_INCREMENT,
    filial_id INT(3),
    dep_id INT(3),
    department_id INT(3),
    pat_in_fil_id INT(3),
    doc_in_fil_id INT(3),
    filial_name VARCHAR(15),
    filial_address VARCHAR(30),
    FOREIGN KEY (pat_in_fil_id) REFERENCES pat_in_fil (pat_in_fil_id) on delete set null,
    FOREIGN KEY (doc_in_fil_id) REFERENCES doc_in_fil (doc_in_fil_id) on delete set null,
    FOREIGN KEY (dep_id) REFERENCES department (dep_id) on delete set null);    
 
insert into patient (patient_id, patient_name, patient_telephone, patient_sex, patient_age) values 
    (1, 'Емельянов М.П.', '89152535817', 'М', 47),
    (2, 'Алексеева А.С.', '89168729620', 'Ж', 28),
    (3, 'Носов Г.М.', '89776643267', 'М', 32),
    (4, 'Чернов А.В.', '89032441725', 'М', 26),
    (5, 'Васин И.С.', '89269093988', 'М', 75),
    (6, 'Семина Н.Д.', '89163376219', 'Ж', 20),
    (7, 'Мишина Р.С.', '89775373701', 'Ж', 43),
    (8, 'Матвеев М.Д.', '89161105400', 'М', 31);
select * from patient;    

insert into doctor (doctor_id, doctor_name, doctor_telephone, doctor_sex, doctor_age, doctor_experience, doctor_job, doctor_room) values 
    (1, 'Зайцева А.А.', '89260808422', 'Ж',28 , 2, 'Хирург', 205),
    (2, 'Астахов Н.Т.', '89163099201', 'М', 41, 15, 'Терапевт', 106),
    (3, 'Емелина И.М.', '89772240014', 'Ж', 43, 17, 'Кардиолог', 304),
    (4, 'Васильев В.В.', '89031857959', 'М', 35, 9, 'Терапевт', 228),
    (5, 'Лунин О.Д.', '89772318957', 'М', 47, 21, 'Хирург', 216),
    (6, 'Головина А.В.', '89267549836', 'Ж', 34, 6, 'Офтальмолог', 327),
    (7, 'Карасева Н.А.', '89159052970', 'Ж', 47, 21, 'Невропатолог', 108); 
select * from doctor;       

insert into pat_in_dep (pat_in_dep_id, patient_id, department_id) values 
    (1, 8, 6),
    (2, 4, 3),
    (3, 1, 2),
    (4, 2, 2),
    (5, 5, 5),
    (6, 6, 1),
    (7, 7, 3),
    (8, 8, 4),
    (9, 5, 2),
    (10, 3, 5);
select * from pat_in_dep;

insert into pat_in_fil (pat_in_fil_id, patient_id, filial_id) values 
    (1, 8, 2),
    (2, 4, 1),
    (3, 1, 2),
    (4, 2, 2),
    (5, 5, 1),
    (6, 6, 1),
    (7, 7, 1),
    (8, 5, 2),
    (9, 3, 1);
select * from pat_in_fil;

insert into doc_in_dep (doc_in_dep_id, doctor_id, department_id) values 
    (1, 2, 1),
    (2, 4, 2),
    (3, 6, 5),
    (4, 1, 3),
    (5, 3, 4),
    (6, 7, 6),
    (7, 5, 3);
select * from doc_in_dep;

insert into doc_in_fil (doc_in_fil_id, doctor_id, filial_id) values 
    (1, 5, 1),
    (2, 1, 1),
    (3, 2, 1),
    (4, 4, 2),
    (5, 3, 2),
    (6, 7, 2),
    (7, 6, 1);
select * from doc_in_fil;

insert into department (dep_id, department_id, pat_in_dep_id, doc_in_dep_id, department_name) values 
    (1, 1, 6, 1, 'Терапевтия'),
    (2, 2, 4, 2, 'Терапевтия'),
    (3, 2, 9, 2,'Терапевтия'),
    (4, 2, 3, 2,'Терапевтия'),
    (5, 3, 2, 4, 'Хирургия'),
    (6, 3, 7, 7, 'Хирургия'),
    (7, 4, 8, 5, 'Кардиология'),
    (8, 5, 5, 3, 'Офтальмология'),
    (9, 6, 1, 6, 'Невропатология'),
    (10, 5, 10, 3, 'Офтальмология');
select * from department;   

insert into filial (fil_id, dep_id, filial_id, department_id, pat_in_fil_id, doc_in_fil_id, filial_name, filial_address) values 
    (1, 5, 1, 3, 2, 1, 'Филиал №1', 'Есенинский бул. 8'),
    (2, 6, 1, 3, 7, 2, 'Филиал №1', 'Есенинский бул. 8'),
    (3, 1, 1, 1, 6, 3, 'Филиал №1', 'Есенинский бул. 8'),
    (4, 10, 1, 5, 9, 7, 'Филиал №1', 'Есенинский бул. 8'),
    (5, 8, 1, 5, 5, 7, 'Филиал №1', 'Есенинский бул. 8'),
    (6, 9, 2, 6, 1, 6, 'Филиал №2', 'Волжский бул. 10'),
    (7, 7, 2, 4, 1, 5, 'Филиал №2', 'Волжский бул. 10'),
    (8, 2, 2, 2, 3, 4, 'Филиал №2', 'Волжский бул. 10'),
    (9, 3, 2, 2, 4, 4, 'Филиал №2', 'Волжский бул. 10'),
    (10, 4, 2, 2, 8, 4, 'Филиал №2', 'Волжский бул. 10');
select * from filial;   








#Проверка корректности бд
delimiter //
create procedure correct ()
begin
select case
when exists (select doctor_id from doc_in_dep group by doctor_id having count(doctor_id) > 1)
then (select doctor_id from doc_in_dep group by doctor_id having count(doctor_id) > 1)
else (select 'Каждый врач относится к одному отделению')
end;
end//
call correct();

select * from patient; 
select * from doctor;   
select * from pat_in_dep;
select * from pat_in_fil;
select * from doc_in_dep;
select * from doc_in_fil;
select * from department;  
select * from filial;

#Запрос 1 - в каких филиалах обслуживается пациент
#-------------------------------------------------
#drop procedure patient_in_fils;
delimiter //
create procedure patient_in_fils (in cur_patient VARCHAR(30))
begin
select distinct filial_name, filial_address from patient inner join pat_in_fil on patient.patient_id = pat_in_fil.patient_id 
	inner join filial on pat_in_fil.filial_id = filial.filial_id
	where patient.patient_name = cur_patient;
end//
call patient_in_fils('Васин И.С.');


#Запрос 2 - средний возраст работников медклиники
#------------------------------------------------
delimiter //
create procedure doctor_average_age (in cur_filial_id INT(3))
begin
select round(avg(doctor_age), 2) as avg_age from doctor inner join doc_in_fil on doctor.doctor_id = doc_in_fil.doctor_id
	where doc_in_fil.filial_id = cur_filial_id;
end//
call doctor_average_age(2);


#Запрос 3 - количество отделений в филиале
#-----------------------------------------
#drop procedure quntity_of_dep_in_fil;
delimiter //
create procedure quntity_of_dep_in_fil (in cur_filial_id INT(3))
begin
select count(department_name) from
	(select distinct department_name from filial inner join department on filial.dep_id = department.dep_id
	where filial_id = cur_filial_id) dep_name;
end//
call quntity_of_dep_in_fil(1);


#Запрос 4 - отделения в филиале
#--------------------------------
delimiter //
create procedure deps_in_fil (in cur_filial_id INT(3))
begin
select distinct department_name from filial inner join department on filial.dep_id = department.dep_id
	where filial_id = cur_filial_id;
end//
call deps_in_fil(1);

#Запрос 5 - получение списка пациентов филиала
#---------------------------------------------
delimiter //
create procedure list_of_pat_in_filial (in cur_fil_name VARCHAR(15))
begin
select distinct patient_name from patient inner join pat_in_fil on patient.patient_id = pat_in_fil.patient_id 
	inner join filial on filial.filial_id = pat_in_fil.filial_id
	where filial_name = cur_fil_name;
end//
call list_of_pat_in_filial('Филиал №1');


#Запрос 6 - получение списка врачей в отделении
#----------------------------------------------
delimiter //
create procedure list_of_doc_in_dep (in cur_department_name VARCHAR(20))
begin
select distinct doctor_name, doctor_job, filial_name, filial_address from doctor inner join doc_in_dep on doctor.doctor_id = doc_in_dep.doctor_id
	inner join department on department.doc_in_dep_id = doc_in_dep.doc_in_dep_id 
		left join filial on department.dep_id = filial.dep_id
		where department_name = cur_department_name;
end//
call list_of_doc_in_dep('Терапевтия');


#Запрос 7 - средний возраст пациентов определенного пола
#-------------------------------------------------------
delimiter //
create procedure avg_age_by_sex (in cur_sex VARCHAR(2))
begin
select avg(patient_age) from patient where patient_sex like cur_sex;
end//
call avg_age_by_sex('Ж');


#Запрос 8 - список врачей и информацию по ним, стаж которых выше определенного числа
#---------------------------------------------------------------
delimiter //
create procedure list_of_doc_with_cur_exp (in cur_experiaence INT(2))
begin
select distinct doctor_name, doctor_telephone, doctor_sex, doctor_age, doctor_experience, doctor_job, doctor_room, filial_name 
	from doctor inner join doc_in_fil on doctor.doctor_id = doc_in_fil.doctor_id 
		inner join filial on doc_in_fil.filial_id = filial.filial_id
		where doctor_experience > cur_experiaence;
end//
call list_of_doc_with_cur_exp(16);


#Запрос 9 - адреса всех филиалов
#-------------------------------
select distinct filial_name, filial_address from filial;


#Запрос 10 - вывести все отделения конкретного филиала на конкретном этаже
#-------------------------------------------------------------------------
#drop procedure deps_on_floor;
delimiter //
create procedure deps_on_floor (in cur_fil VARCHAR(15), cur_floor VARCHAR(3))
begin
select distinct department_name from department inner join doc_in_dep on department.department_id = doc_in_dep.department_id inner join doctor on
doctor.doctor_id = doc_in_dep.doctor_id
	where (doctor.doctor_id, doctor_room) in 
		(select distinct doc_in_fil.doctor_id, doctor_room from doctor inner join doc_in_fil on doctor.doctor_id = doc_in_fil.doctor_id 
		inner join filial on doc_in_fil.filial_id = filial.filial_id 
		where filial_name = cur_fil and doctor_room like cur_floor);
end//
call deps_on_floor('Филиал №1', '2%');


#Запрос 11 - количество врачей определенного пола
#------------------------------------------------
delimiter //
create procedure quan_of_doc (in cur_doc_sex VARCHAR(2))
begin
select count(doctor_id) from doctor 
where doctor_sex = cur_doc_sex;
end//
call quan_of_doc('М');


#Запрос 12 - вывод информации по конкретному пациенту (личные данные, какие отделения помещает, какие филиалы)
#-------------------------------------------------------------------------------------------------------------
delimiter //
create procedure all_info_about_patient (in cur_patient VARCHAR(30))
begin
select distinct patient_name, patient_telephone, patient_sex, patient_age, department_name, filial_name
from patient inner join pat_in_dep on
	patient.patient_id = pat_in_dep.patient_id inner join department on pat_in_dep.department_id = department.department_id 
		inner join pat_in_fil on patient.patient_id = pat_in_fil.patient_id 
			inner join filial on department.dep_id = filial.dep_id
				where patient_name = cur_patient;
end//
call all_info_about_patient('Матвеев М.Д.');


#Запрос 13 - вывести список всех врачей конкретной должности
#------------------------------------------------------------
delimiter //
create procedure list_of_doc_with_job (in cur_job VARCHAR(20))
begin
select distinct doctor_name from doctor
where doctor_job like cur_job;
end//
call list_of_doc_with_job('Терапевт');


#Запрос 14 - вывести адреса филиалов, в которых есть определенное отделение
#--------------------------------------------------------------------------
delimiter //
create procedure fils_with_cert_dep (in cur_dep VARCHAR(20))
begin
select distinct filial_name, filial_address from filial inner join department on filial.department_id = department.department_id
where department_name = cur_dep;
end//
call fils_with_cert_dep('Хирургия');


#Запрос 15 - список врачей филиала
#---------------------------------
#drop procedure list_of_doc_in_fil;
delimiter //
create procedure list_of_doc_in_fil (in cur_fil VARCHAR(15))
begin
select distinct doctor_name, doctor_job from doctor inner join doc_in_fil on doctor.doctor_id = doc_in_fil.doctor_id
	inner join filial on filial.filial_id = doc_in_fil.filial_id
	where filial_name = cur_fil;
end//
call list_of_doc_in_fil('Филиал №1');




select * from patient; 
select * from doctor;   
select * from pat_in_dep;
select * from pat_in_fil;
select * from doc_in_dep;
select * from doc_in_fil;
select * from department;  
select * from filial;

#-------------------------------УДАЛЕНИЕ ЗАПИСЕЙ И ТАБЛИЦ--------------------------
delete from pat_in_fil;
delete from doc_in_fil;
delete from filial;
delete from department;
delete from pat_in_dep;
delete from doc_in_dep;
delete from patient;
delete from doctor;

drop table pat_in_fil;
drop table doc_in_fil;
drop table filial;
drop table department;
drop table pat_in_dep;
drop table doc_in_dep;
drop table patient;
drop table doctor;
#--------------------------------------------------------------------------------------

#Запрос 16 - добавить в бд нового пациента
#-----------------------------------------
#drop procedure add_patient;
delimiter //
create procedure add_patient (in pat_name VARCHAR(30), pat_phone VARCHAR(12), pat_sex VARCHAR(2), pat_age INT(3), fil_name VARCHAR(15), 
dep_name VARCHAR(20))
begin
insert into patient (patient_name, patient_telephone, patient_sex, patient_age)
	values (pat_name, pat_phone, pat_sex, pat_age);

insert into pat_in_fil (patient_id, filial_id)
	values ((select patient_id from patient where patient_name = pat_name),
			(select distinct filial_id from filial where filial_name = fil_name));


insert into pat_in_dep (patient_id, department_id)
	values ((select patient_id from patient where patient_name = pat_name),
			(select distinct department_id from department 
				where department_name = dep_name and department_id in (select department_id from filial 
					where filial_id = (select distinct filial_id from filial where filial_name = fil_name))));

#----------
create table dep_id_table (
	dep_id_table_id INT(3) PRIMARY KEY AUTO_INCREMENT,
    depart_id INT(3)
);
insert into dep_id_table (depart_id)
	select distinct department_id from department 
				where department_name = dep_name and department_id in (select department_id from filial 
					where filial_id = (select distinct filial_id from filial where filial_name = fil_name));
                    
create table doc_dep_id_table (
	doc_dep_id_table_id INT(3) PRIMARY KEY AUTO_INCREMENT,
    docs_id INT(3)
);
insert into doc_dep_id_table (docs_id)
	select doc_in_dep_id from doc_in_dep where department_id = (select depart_id from dep_id_table) limit 1;
#-----------

insert into department (department_id, pat_in_dep_id, doc_in_dep_id, department_name)
	values ((select depart_id from dep_id_table),
			(select pat_in_dep_id from pat_in_dep 
				where patient_id = (select patient_id from patient where patient_name = pat_name) 
					and department_id = (select depart_id from dep_id_table)),
			(select docs_id from doc_dep_id_table),
            dep_name);

create table fil_id_table (
	fil_id_table_id INT(3) PRIMARY KEY AUTO_INCREMENT,
    filial_id_table INT(3),
    filial_name_table VARCHAR(15),
    filial_address_table VARCHAR(30)
);
insert into fil_id_table (filial_id_table, filial_name_table, filial_address_table) 
	select distinct filial_id, filial_name, filial_address from filial where filial_name = fil_name;
    
create table doc_in_fil_table (
	doc_in_fil_table INT(3) PRIMARY KEY AUTO_INCREMENT,
    docs_in_fil_id INT(3)
);
insert into doc_in_fil_table (docs_in_fil_id) 
	select distinct doctor_id from doc_in_fil where filial_id = (select distinct filial_id from filial where filial_name = fil_name);
#select * from doc_in_fil_table;

insert into filial (filial_id, dep_id, pat_in_fil_id, doc_in_fil_id, department_id, filial_name, filial_address)
	values ((select filial_id_table from fil_id_table),
			(select dep_id from department where pat_in_dep_id = (select pat_in_dep_id from pat_in_dep where patient_id = 
				(select patient_id from patient where patient_name = pat_name)
                group by pat_in_dep_id
                order by pat_in_dep_id desc limit 1)),
			(select distinct pat_in_fil_id from pat_in_fil where patient_id = (select patient_id from patient where patient_name = pat_name)),
            (select docs_in_fil_id from doc_in_fil_table limit 1),
            (select depart_id from dep_id_table),
            (select filial_name_table from fil_id_table),
            (select filial_address_table from fil_id_table));
            
delete from doc_in_fil_table;
drop table doc_in_fil_table;
            
delete from dep_id_table;
delete from doc_dep_id_table;
delete from fil_id_table;
drop table dep_id_table;
drop table doc_dep_id_table;
drop table fil_id_table;

end//
call add_patient('Темин В.Ц.', '89456789213', 'М', 31, 'Филиал №1', 'Хирургия');


#Запрос 17 - Удалить пациента из бд
#----------------------------------
delimiter //
create procedure delete_patient (in pat_name VARCHAR(30))
begin
delete from patient where patient_name = pat_name;
end//
call delete_patient ('Васин И.С.');


#Запрос 18 - удалить конкретную запись пациента к врачу
#------------------------------------------------------
#drop procedure delete_patient_from_department;
delimiter //
create procedure delete_patient_from_department(in pat_name VARCHAR(30), dep_name VARCHAR(20), fil_name VARCHAR(20))
begin
create table fil_table (
	fil_table_id INT(3) PRIMARY KEY AUTO_INCREMENT,
    deps_id INT(3)
);
insert into fil_table (deps_id)
	select distinct department_id from filial where filial_name = fil_name;
#select * from fil_table;
    
create table dep_table (
	dep_table_id INT(3) PRIMARY KEY AUTO_INCREMENT,
    depar_id INT(3)
);
insert into dep_table (depar_id)
	select distinct department_id from department where department_name = dep_name and department_id in (select deps_id from fil_table);
#select * from dep_table;

delete from pat_in_dep where patient_id = (select patient_id from patient where patient_name = pat_name) 
	and department_id = (select depar_id from dep_table);

delete from fil_table;
delete from dep_table;
drop table fil_table;
drop table dep_table;
end//
call delete_patient_from_department('Матвеев М.Д.', 'Кардиология', 'Филиал №2');


#Запрос 19 - записать пациента к еще одному отделению 
#----------------------------------------------------
drop procedure add_patient_to_department;
delimiter //
create procedure add_patient_to_department (in pat_name VARCHAR(30), dep_name VARCHAR(20), fil_name VARCHAR(20))
begin
#возня с pat_in_dep
create table deps_in_fil_table (
	deps_in_fil_table_id INT(3) PRIMARY KEY AUTO_INCREMENT,
    depar_id INT(3)
);
insert into deps_in_fil_table (depar_id)
	select distinct department_id from filial where filial_name = fil_name;
#select * from deps_in_fil_table;

insert into pat_in_dep (patient_id, department_id)values
	((select patient_id from patient where patient_name = pat_name),
	 (select distinct department_id from department where department_name = dep_name and department_id in (select depar_id from deps_in_fil_table)));
#select * from pat_in_dep;
	
#возня с pat_in_fil
create table t (
	t_id INT(3) PRIMARY KEY AUTO_INCREMENT,
    patient_id INT(3),
    filial_id INT(3)
);
insert into t (patient_id, filial_id) values
	((select patient_id from patient where patient_name = pat_name),
     (select distinct filial_id from filial where filial_name = fil_name)); 
#select * from t;

create table pat_in_fil_table (
	pat_in_fil_table_id INT(3) PRIMARY KEY AUTO_INCREMENT,
    patient_id INT(3),
    filial_id  INT(3)
);
insert into pat_in_fil_table (patient_id, filial_id)
	select patient_id, filial_id from pat_in_fil;
#select * from pat_in_fil_table;
     
create table new_t (
	new_t_id INT(3) PRIMARY KEY AUTO_INCREMENT,
    patient_id INT(3),
    filial_id INT(3)
);
insert into new_t (patient_id, filial_id) 
	select patient_id, filial_id from t where (patient_id, filial_id) not in (select patient_id, filial_id from pat_in_fil_table);
#select * from new_t;

insert into pat_in_fil (patient_id, filial_id)
	select patient_id, filial_id from new_t;
     
#возня с department
create table dep_id_table (
	dep_id_table_id INT(3) PRIMARY KEY AUTO_INCREMENT,
    depart_id INT(3)
);
insert into dep_id_table (depart_id)
	select distinct department_id from department 
				where department_name = dep_name and department_id in (select department_id from filial 
					where filial_id = (select distinct filial_id from filial where filial_name = fil_name));

create table doc_dep_id_table (
	doc_dep_id_table_id INT(3) PRIMARY KEY AUTO_INCREMENT,
    docs_id INT(3)
);
insert into doc_dep_id_table (docs_id)
	select doc_in_dep_id from doc_in_dep where department_id = (select depart_id from dep_id_table) limit 1;

insert into department (department_id, pat_in_dep_id, doc_in_dep_id, department_name) values
	((select depart_id from dep_id_table),
     (select pat_in_dep_id from pat_in_dep 
				where patient_id = (select patient_id from patient where patient_name = pat_name) 
					and department_id = (select depart_id from dep_id_table)),
     (select docs_id from doc_dep_id_table),
     dep_name);

#возня c filial
create table fil_id_table (
	fil_id_table_id INT(3) PRIMARY KEY AUTO_INCREMENT,
    filial_id_table INT(3),
    filial_name_table VARCHAR(15),
    filial_address_table VARCHAR(30)
);
insert into fil_id_table (filial_id_table, filial_name_table, filial_address_table) 
	select distinct filial_id, filial_name, filial_address from filial where filial_name = fil_name;
                   
create table doc_in_fil_table (
	doc_in_fil_table INT(3) PRIMARY KEY AUTO_INCREMENT,
    docs_in_fil_id INT(3)
);
insert into doc_in_fil_table (docs_in_fil_id) 
	select doctor_id from doc_in_fil where filial_id = (select distinct filial_id from filial where filial_name = fil_name);

insert into filial (filial_id, dep_id, pat_in_fil_id, doc_in_fil_id, department_id, filial_name, filial_address)
	values ((select filial_id_table from fil_id_table),
			(select dep_id from department where pat_in_dep_id = (select pat_in_dep_id from pat_in_dep where patient_id = 
				(select patient_id from patient where patient_name = pat_name)
                group by pat_in_dep_id
                order by pat_in_dep_id desc limit 1)),
			(select pat_in_fil_id from pat_in_fil where patient_id = (select patient_id from patient where patient_name = pat_name)),
            (select docs_in_fil_id from doc_in_fil_table limit 1),
            (select depart_id from dep_id_table),
            (select filial_name_table from fil_id_table),
            (select filial_address_table from fil_id_table));
            
delete from doc_in_fil_table;
drop table doc_in_fil_table;
            
delete from deps_in_fil_table;      
delete from dep_id_table;
delete from doc_dep_id_table;
delete from fil_id_table;
drop table deps_in_fil_table;
drop table dep_id_table;
drop table doc_dep_id_table;
drop table fil_id_table; 
delete from t;
delete from pat_in_fil_table;
delete from new_t;
drop table t;
drop table pat_in_fil_table;
drop table new_t;    
end//
call add_patient_to_department('Матвеев М.Д.', 'Терапевтия', 'Филиал №2');


#Запрос 20 - вся информация о конкретном враче
#---------------------------------------------
delimiter //
create procedure all_info_about_doctor (in cur_doctor VARCHAR(30))
begin
select distinct doctor_name, doctor_telephone, doctor_sex, doctor_age, doctor_experience, doctor_job, doctor_room, department_name, filial_name
from doctor inner join doc_in_dep on
	doctor.doctor_id = doc_in_dep.doctor_id inner join department on doc_in_dep.department_id = department.department_id 
		inner join doc_in_fil on doctor.doctor_id = doc_in_fil.doctor_id 
			inner join filial on department.dep_id = filial.dep_id
				where doctor_name = cur_doctor;
end//
call all_info_about_doctor('Емелина И.М.');





create table doc_in_fil_table (
	doc_in_fil_table INT(3) PRIMARY KEY AUTO_INCREMENT,
    docs_in_fil_id INT(3)
);
insert into doc_in_fil_table (docs_in_fil_id) 
	select doctor_id from doc_in_fil where filial_id = (select distinct filial_id from filial where filial_name = fil_name);

insert into filial (filial_id, dep_id, pat_in_fil_id, doc_in_fil_id, department_id, filial_name, filial_address)
	values ((select filial_id_table from fil_id_table),
			(select dep_id from department where pat_in_dep_id = (select pat_in_dep_id from pat_in_dep where patient_id = 
				(select patient_id from patient where patient_name = pat_name)
                group by pat_in_dep_id
                order by pat_in_dep_id desc limit 1)),
			(select pat_in_fil_id from pat_in_fil where patient_id = (select patient_id from patient where patient_name = pat_name)),
            (select docs_in_fil_id from doc_in_fil_table limit 1),
            (select depart_id from dep_id_table),
            (select filial_name_table from fil_id_table),
            (select filial_address_table from fil_id_table));
            
delete from doc_in_fil_table;
drop table doc_in_fil_table;
            
            
            
            
            
            
#+++++++++++++++++++++++++++++++++++++++++++
#+++++++++++++++++++++++++++++++++++++++++++
#+++++++++++++++++++++++++++++++++++++++++++
