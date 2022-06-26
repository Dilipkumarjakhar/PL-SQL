### Declaring & Initializing & Using Variables (Code Samples)
***===================DECLARING VARIABLES===================***
```
SET SERVEROUTPUT ON;
DECLARE 
    v varchar2(20) := 2 + 25 * 3;
BEGIN
    dbms_output.put_line(v);
END;
```
-----------------------===================-----------------------
```
DECLARE 
    v_text varchar2(50) NOT NULL DEFAULT 'Hello';
    v_number1 number := 50;
    v_number2 number(2) := 50.42;
    v_number3 number(10,2) := 50.42;
    v_number4 PLS_INTEGER := 50;
    v_number5 BINARY_float := 50.42;
    v_DATE1 DATE := '22-NOV-18 12:01:32';
    v_DATE2 timestamp := systimestamp;
    v_DATE3 timestamp(9) WITH TIME ZONE := systimestamp;
    v_DATE4 interval day(4) to second (3) := '124 02:05:21.012 ';
    v_DATE5 interval year to month := '12-3';
```
```
BEGIN
    V_TEXT := 'PL/SQL' || 'Course';
    DBMS_OUTPUT.PUT_LINE(V_TEXT);
    DBMS_OUTPUT.PUT_LINE(v_number1);
    DBMS_OUTPUT.PUT_LINE(v_number2);
    DBMS_OUTPUT.PUT_LINE(v_number3);
    DBMS_OUTPUT.PUT_LINE(v_number4);
    DBMS_OUTPUT.PUT_LINE(v_number5);
    DBMS_OUTPUT.PUT_LINE(v_DATE1);
    DBMS_OUTPUT.PUT_LINE(v_DATE2);
    DBMS_OUTPUT.PUT_LINE(v_DATE3);
    DBMS_OUTPUT.PUT_LINE(v_DATE4);
    DBMS_OUTPUT.PUT_LINE(v_DATE5);
    END;
```

***----------------USING BOOLEAN DATA TYPE in PL/SQL----------------***
```
DECLARE
    v_boolean boolean := true;
BEGIN
    dbms_output.put_line(sys.diutil.bool_to_int(v_boolean));
END;
```
----------------==================================---------------

```
declare
num number :=-1;
name varchar(20) :='dilip';
--not null default 'go goa gone';
begin
if num >10 or name='dilip' then
dbms_output.put_line('haa ' || num);
elsif num >20 then 
dbms_output.put_line(num);
else
if num<0 then
dbms_output.put_line(num);
else
dbms_output.put_line(num);
end if;
end if;
end;
```
***when condition***
```
declare
name varchar(20) :='aman';
v_salary number;
begin
v_salary :=case
when name='dilip' then 0.2
when name='aman' then 100
else 0
end;
dbms_output.put_line(v_salary);
end;
```
***-------CASE EXPRESSIONS----***
```
declare
  v_job_code varchar2(10) := 'SA_MAN';
  v_salary_increase number;
begin
  v_salary_increase := case v_job_code 
    when 'SA_MAN' then 0.2
    when 'SA_REP' then 0.3
    else 0
  end;
  dbms_output.put_line('Your salary increase is : '|| v_salary_increase);
end;
```
***----SEARCHED CASE EXPRESSION------***'
```
declare
  v_job_code varchar2(10) := 'IT_PROG';
  v_department varchar2(10) := 'IT';
  v_salary_increase number;
begin
  v_salary_increase := case  
    when v_job_code = 'SA_MAN' then 0.2
    when v_department = 'IT' and v_job_code = 'IT_PROG' then 0.3
    else 0
  end;
  dbms_output.put_line('Your salary increase is : '|| v_salary_increase);
end;
```

***-------CASE STATEMENTS-------***
```
declare
  v_job_code varchar2(10) := 'IT_PROG';
  v_department varchar2(10) := 'IT';
  v_salary_increase number;
begin
  case  
    when v_job_code = 'SA_MAN' then 
      v_salary_increase := 0.2;
      dbms_output.put_line('The salary increase for a Sales Manager is : '|| v_salary_increase);
    when v_department = 'IT' and v_job_code = 'IT_PROG' then 
      v_salary_increase := 0.2;
      dbms_output.put_line('The salary increase for a Sales Manager is : '|| v_salary_increase);
    else 
      v_salary_increase := 0;
      dbms_output.put_line('The salary increase for this job code is : '|| v_salary_increase);
  end CASE;
end;
```
-------------------------------------------------------------------------------

***Basic Loops (Code Samples)***
-------------------------BASIC LOOPS--------------------------
```
declare
v_counter number(2) := 1;
begin
  loop
    dbms_output.put_line('My counter is : '|| v_counter);
    v_counter := v_counter + 1;
    --if v_counter = 10 then
    --  dbms_output.put_line('Now I reached : '|| v_counter);
    --  exit;
    --end if;
    exit when v_counter > 10;
  end loop;
end;
```
--------------------------------------------------------------

***While Loops (Code Samples)***
------------------------------WHILE LOOPS-------------------------------
```
declare
v_counter number(2) := 1;
begin
  while v_counter <= 10 loop
    dbms_output.put_line('My counter is : '|| v_counter);
    v_counter := v_counter + 1;
   -- exit when v_counter > 3;
  end loop;
end;
```
-------------------------------------------------------------------------
***for loop***
```
begin
for i in 1..3 loop
dbms_output.put_line('the counter value: '|| i)
end loop;
end;
```
output:1:-
- the counter value:1
- the counter value:2
- the counter value:3

-----------------------------FOR LOOPS-----------------------------
```
begin
  for i in REVERSE 1..3 loop
    dbms_output.put_line('My counter is : '|| i);
  end loop;
end;
```
-------------------------------------------------------------------
