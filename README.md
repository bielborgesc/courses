# Courses

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 14.1.2.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The application will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via a platform of your choice. To use this command, you need to first add a package that implements end-to-end testing capabilities.

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI Overview and Command Reference](https://angular.io/cli) page.

## Como testar

[1] Crie um usuário do tipo professor, e outro usuário do tipo Aluno (emails devem ser diferentes)

[2] Já existem diversos cursos cadastrados, porém, como professor, crie cursos navegando até a rota:
    /professor/novo-curso

    - Após criar o curso, insira as aulas em
        /professor/curso/:courseId/aulas (caso não seja redirecionado automaticamente)

[3] Como aluno, você pode visualizar:

    - Todos os cursos cadastrados em:
        pagina principal

    - Visualizar seus cursos em:
        /meus-cursos

    - Comprar curso
        /aluno/curso/:courseId/comprar

    - Assistir as aulas do curso
        /aluno/curso/:courseId/aulas

    - Atenção
        O objetivo não é fazer todo o componente de compra, e sim simular apenas um crud na tabela de relação de cursos do usuário

## BACKEND

:bulb: In this directory has a [Insomnia.json] file. Import it into your Insominia to test routes

### Routes - Auth

    - Register
        [POST] /auth/register

    - Login
        [POST] /auth/login

### Routes - Teacher

:warning: headers -> Authorization [token]

    - Create Course
        [POST] /me/teacher/courses/

    - Create Lesson
        [POST] /me/teacher/courses/:course_id/lesson

    - List Courses
        [GET] /me/teacher/courses/

### Routes - Student

:warning: headers -> Authorization [token]

    - List courses
        [GET] /me/student/courses/

    - Buy course
        [GET] /me/student/courses/buy/:course_id

    - Find one course
      * Accessing with the token, listing a course, the route shows the url of the videos of each lesson
        [GET] /me/student/courses/:course_id

    - Access lesson
        [GET] /me//student/courses/play/:lesson_id

### Routes main

    - List all courses
        [GET]  /courses

    - Find One Course
        [GET]  /courses/:course_id
