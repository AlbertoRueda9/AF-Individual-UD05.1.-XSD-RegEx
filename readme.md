Vamos a diseñar un xml simple que contenga un elemento raíz llamado usuarios, dentro de este, saldrán varios
varios elementos usuarios con su correspondiente id. Cada usuario tendrá como se nos pide en el ejercicio
su email, código postal, teléfono, nombre de usuario y contraseña, para todo ello necesitaremos un elemento.

En cuanto al XSD, necesitaremos un tipo complejo para definir "usuario" y definiremos el id como un entero positivo.

Los elementos dentro de usuario, los definiremos en un tipo simple, donde definiremos las restricciones de cada uno de ellos. 

En cuanto el email, necesitaremos la primera parte, un usuario, que sea minuscula y pueda incluir numeros y algunos simbolos, seguido de un dominio correcto y na extensión de al menos dos letras. Por ello su expresión es: [A-Za-z0-9.]+@[A-Za-z0-9.-]+\.[A-Za-z]{2,}"

En cuanto al número de teléfono, hemos decidido que el prefijo +34 sea opcional. El teléfono tendrá 9 digitos pero el primero debera empezar por un número entre el 6 y el 9, al ser un número español. Esta sería la expresión regular: (\+34 ?)?[6-9][0-9]{8}.

En españa el código postal está formado por 5 digitos, los dos primero identifican a la provincia, por lo que nos deberemos mover entre un rango de 01 a 52. Los ultimos tres digitos pueden ir del 001 al 999. Por tanto esta sería la expresión regular: (0[1-9]|[1-4][0-9]|5[0-2])[0-9]{3}.

El nombre de usuario he establecido que tenga un mínimo de 8 carácteres y un máximo de 20, debiendo ser el primero una letra minúscula, pudiendo contener caracteres numéricos y puntos o guiones bajos como ocurre en muchas redes sociales. esta sería la expresión regular : [a-z][a-z0-9._]*.

Por último la contraseña, deberá contener mínimo 8 caracteres que deben incluir al menos una letra mayúscula,una minúscula, un número y un simbolo. Para ello necesitaremos establecer cuatro patrones en los que se pida cada una de estas restricciones. Sería los siguientes :[a-z], [A-Z], [0-9], [^A-Za-z0-9].
       