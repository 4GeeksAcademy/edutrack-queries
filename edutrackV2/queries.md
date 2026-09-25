1-
```sql
select s.name, c.title, e.completion_percentage from enrollments e
inner join students s on s.id = e.student_id
inner join courses c on c.id = e.course_id
```

2-
```sql
select s.name, s.email, c.title, e.passed from students s 
inner join enrollments e on e.student_id = s.id
inner join courses c on c.id = e.course_id
where e.passed = true 
```

3-
```sql
select c.instructor_name, avg(e.completion_percentage) as promedio_completado from courses c
inner join enrollments e on e.course_id = c.id
GROUP BY c.instructor_name
order by promedio_completado desc
```

4-
```sql
SELECT
    s.name
FROM students s
LEFT JOIN enrollments e
    ON s.id = e.student_id
WHERE e.id IS NULL;
```

5-
```sql
select c.id, c.title from courses c
left join enrollments e on e.course_id = c.id
where e.id is NULL

```

6-
```sql
select s.name as student_name, count(e.id) as cantidad_cursos_inscritos from students s
inner join enrollments e on e.student_id = s.id
group by student_name
having count(e.id) > 1
```

7-
```sql
select c.category, sum(c.monthly_fee) from courses c
inner join enrollments e on e.course_id = c.id
group by category

```

8-
```sql
select c.instructor_name, count(distinct e.student_id) as cantidad_estudiantes from courses c
inner join enrollments e on e.course_id = c.id
group by instructor_name
order by cantidad_estudiantes desc
```

9-
```sql
select e.id, e.student_id from enrollments e
left join students s on s.id = e.student_id
where s.id is NULL
```

10-
```sql
select e.id, e.course_id from enrollments e
left join courses c on c.id = e.course_id
where c.id is NULL
```

