## Consultas realizadas

Test de creación

```sql
SELECT * FROM enrollments LIMIT 5;
```

Query 1:

```sql
Select student_name, student_email, completion_percentage from enrollments where course_title = 'Intro to Python'
```

Query 2:
```sql
select * from enrollments where completion_percentage < 10
```

Query 3:
```sql
select * from enrollments where instructor is null
```

Query 4:
```sql
select * from enrollments where passed is false order by completion_percentage desc limit 5
```

Query 5:
```sql
select * from enrollments where enrollment_date > '2026-01-01' order by enrollment_date desc
```
O, sin hardcodear la fecha en la query:
```sql
SELECT *
FROM enrollments
WHERE enrollment_date >= CURRENT_DATE - INTERVAL '1 year'
ORDER BY enrollment_date DESC;
```

Query 6:
```sql
insert into enrollments values (18, 3, 'Lucia Fernandes', 'lucia.fernandes@student.edutrack.com', 5, 'Advanced Python', 'Programming', '2025-04-01', 0, false, 69.99, 'Carlos Vega')
```

Query 7:
```sql
update enrollments set instructor = 'Pending assignment' where instructor is null
```

Query 8:
```sql
SELECT * FROM enrollments WHERE student_email LIKE '%@test.com';

delete from enrollments where student_email like '%@test.com'
```

Query 9:
```sql
select category, count(*) as cantidad_inscripciones from enrollments group by category
```

Query 10:
```sql
select course_title, avg(completion_percentage) as promedio_curso from enrollments group by course_title order by (promedio_curso) asc 
```

Query 11:
```sql
select course_title, count(course_id) as Inscriptos from enrollments group by course_title having count(course_id) > 3
```

Query 12:
```sql
select category, sum(monthly_fee_paid) as total_ingresos_mensual from enrollments group by category order by total_ingresos_mensual desc
```
## Resultados obtenidos
- Revisar /queries_result.md