## 4 Agosto 2024

la estrategia de branching es enfocada a un equipo de 4 personas, lo cual puede que el manejo de las ramas sea sencillo por que no son muchas personas manejando el codigo fuente pero si se tendría un orden al momento de probar en los diferentes ambientes, para esto inicialmente planteo el Git Flow

planteo este porque al ser mas de 2 personas en el equipo, se tiene que realizar revisiones por feature de cada uno y al momento de realizar un PR a develop o main, se debe realizar una revisión del codigo para que este pueda pasar sin problemas y ademas de crear pruebas unitarias para evitar bugs al momento de fusionar ramas

hay mas tipos de branching management pero algo mas sencillo pueda ocasionar problemas al no mantener tantas restricciones (como github flow)

### Branches

- main
- develop
- feature/**
- release/**
- hotfixes/**

main = la rama principal que tendrá todo el codigo fuente que estará en produccion

develop = rama hija de main que contiene una copia del codigo para que los desarrolladores puedan tener acceso al ultimo codigo actual

feature/** = ramas hijas de develop, cada desarrollador tendrá a su disposición para poder crear sus funcionalidades, se vuelven a integrear a develop

release/x.x.x = rama con los nuevos cambios de todos los desarrolladores

estos se integran a main junto a un tag para diferenciarlo en sus commits

hotfixes/** = rama hija de main que se centra en arreglar los errores de forma inmediata sin necesidad de atravesar de nuevo el proceso de feature-develop-releases 

