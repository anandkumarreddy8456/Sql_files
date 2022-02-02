create table Faculty(
id int,
Name varchar(100),
subject varchar(100),
Age int);
insert into Faculty (id ,Name ,subject ,Age) values(1,"Ramesh","Maths",25);
insert into Faculty (id ,Name ,subject ,Age) values(2,"Raju","Science",29);
insert into Faculty (id ,Name ,subject ,Age) values(3,"Rahul","Social",31);
insert into Faculty (id ,Name ,subject ,Age) values(4,"Rathod","Social",21);
insert into Faculty (id ,Name ,subject ,Age) values(5,"Anand","Maths",24);
select * from Faculty;
show tables;
select name from Faculty 
where subject='Maths'
order by age ASC;
select * from faculty
where subject="Science"
order by name asc;
select * from faculty
where subject='Maths' or subject='Science' order by name asc;
select * from faculty
where not name='Anand';
select * from faculty
where not subject='Maths' And not subject="Science";
insert into faculty(id,Name,Subject,Age) values(6,null,'Science',null);
update faculty
set name='Harsh' ,Age='29'
where id=6;
select * from faculty;
update faculty
set name='Harish'
where id=6;
delete from faculty where id=5;
insert into faculty(id,name,subject,age) values(5,'Anand Reddy','Social',23);
select * from faculty
where subject="social" order by age asc
limit 2;
select Min(age) from faculty; /*Minum Value Syntax*/
select Max(age) from faculty;/*Maximum Values Syntax/
select count(name) from faculty 
where subject='Social';/*Count Statement */
select * from faculty
where name like '%' order by name desc;

select * from faculty
where name in ("Anand Reddy");
 
update faculty
set name="Anand" 
where id=5;
 
 select * from faculty;
 
 select * from faculty
 where name in ("rahul");

select * from faculty
where age between 20 and 25;


select * from student;
insert into student(Student_id,Student_Name,Student_Course,email) values (5,'Sandeep','Business Analyast','sandeepmama@gmail.com');
delete from student where Student_name='Sandeep';
show tables;
select Student_id as sid, Student_Name as sname
from student;
select id as fid,name as fname
from faculty;

select s.Student_id,s.Student_Name,f.id,f.name
from student as s,faculty as f
where s.Student_name=f.name;

select Student.Student_id,faculty.Name
from student
inner join faculty on Student.Student_id=faculty.id;

select student.Student_Name,faculty.subject
from student
inner join faculty on Student.student_id=faculty.id;

select Student.Student_Course,faculty.Name
from student
left join faculty on student.Student_id=faculty.id
order by student.Student_id;

select student.email,faculty.Name
from student
right join faculty on student.Student_id=faculty.id
order by faculty.id;