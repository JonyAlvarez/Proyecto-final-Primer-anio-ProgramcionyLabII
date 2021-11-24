# Proyecto-final-Primer-anio-ProgramcionyLabII


INFORME PROYECTO FINAL.
Leandro Bovino    -     Jonathan Alvarez

ESTRUCTURAS UTILIZADAS:
    typedef struct{
        char palabra[20];
        int frecuencia;
    }pyf;
    
    typedef struct{
        char palabra[20]
        int idDOC;
    int pos;
    
    }termino;
     typedef struct nodoT{
        int idDOC;
        int pos;
    struct nodoT* sig;
    }nodoT ;
    
    typedef struct nodoA{
        char palabra[20];
        int frecuencia; //cantidad de nodos de la lista
        struct nodoA* der;
        struct nodoA* izq;
    }nodoA;




Librerías y sus funciones:

Librería motor: 
    •         void puntoCero(termino *arr, int *validos, nodoA **arbol) : Carga el diccionario y el motor de búsqueda.
    •          nodoT *crearNodoOcurrencias(termino palabra) : Crea un nodo de la estructura nodoT
    •          nodoA *crearNodoPalabras(char* palabra) : Crea un nodo de la estructura nodoA
    •          termino agregarTermino(termino t) : Crea una instancia de la estructura Termino
    •          void cargarDiccionario(termino arr[], int *validos, char *archivoIds) :

    Recibe un arreglo de palabras(términos), un puntero a validos para luego devolverle la cantidad de términos cargados en el arreglo, y el nombre de un archivo para cargar los ID’s.  Se encarga de pedir los archivos de texto y con esos archivos, cargar el array de términos. Luego con ese array carga el archivo de diccionario a través de la función 
    void pasarTerminosArchivo(termino *terminos, int validos, int idDoc).

    •          void insertarArbolOrdenado(nodoA **arbolDiccionario, char *palabra) : Inserta de forma ordenada un nodo en el arbol.
    •          void cargaDeOcurrencias(nodoA **arbolDiccionario, termino t) : Se encarga a través de una función en su interior de insertar los nodos en la lista.
    •          void cargarMotorBusqueda(char *nombreArchivo, nodoA **lista) : Carga el motor de búsqueda (árbol y lista) con las dos funciones anteriores.


    Librería consignas usuario:
    •      void retornarIdMayor(char  *nombreArchivo) : Retorna el ID mayor (ultimo agregado).
    •      int verSiYaEstaLaId(int *IDs, int validos, int check) : Comprueba que no se pida la misma ID más de una vez.
    •      int buscarPalabraEnDiccionario(nodoA *arbolDiccionario, char *palabra) : Verifica que la palabra pasada exista en el árbol.

            
1.
 
                void puntoUno(); Se encarga de todas las “subfunciones”.

    •      void buscarNodoUnID(nodoA *arbol, char *palabra, int idArchivo) : Busca una palabra en el árbol.
    •      void verListaUnID(nodoT *lista, int idArchivo) : Muestra las veces que está la palabra en el documento que se pasa por ID.
    •      void pedirUnaPalabra(char *palabra) : Pide una palabra al usuario
    •      void pedirID() : Pide el ID del documento en el que quiera buscar el usuario, con verificaciones.

2.
 
                void puntoDos(); Se encarga de todas las “subfunciones”.

    •      void buscarNodoVariosID(nodoA* arbol, char *palabra, int *idArchivo, int validos) : Busca una palabra en el árbol.
    •      void verListaVariosID(nodoT *lista, int* idsArchivo, int validos, char* palabra) : Por cada id pasado en por parámetro en el arreglo idsArchivo, busca en la lista las que sean iguales y las imprime.
    •      Int pedirVariosID(int id, int *archivoElegido) : Pide al usuario varios ID (Cuantos el usuario quiera agregar)

3.
 
                void puntoTres(); Se encarga de todas las “subfunciones”.

    •      void  pedirVariasPalabras(char palabras[5][20]) : Pide varias palabras al usuario.

4.
 
                void puntoCuatro(); Se encarga de todas las “subfunciones”.

    •      void buscarUnaFrase(nodoA *arbol) :

    Pide una frase y se encarga de llamar las demás funciones para ver si la frase existe en un documento. Carga una matriz con todas las posiciones de cada palabra de la frase pedidas.

    •      void buscarNodoUnIDYRetornar(nodoA *arbol, char *palabra, int idArchivo, int *posiciones) : Busca una palabra, y cuando la encuentra devuelve el numero de veces que esta esa palabra en el documento con ID que se haya pasado por argumento.
    •      void buscarPosicionesFrase(nodoT *lista, int idArchivo, int *posiciones) : Llena el array de posiciones con las posiciones de la palabra, devuelve los validos.
    •      Int verSiSeEncontroLaFrase(int validos, int posicionesFrase[][200], int *validosPosiciones) : Checkea con cada posición de cada palabra de la frase si existen en el documento todas las palabras de manera contigua.

5.
 
                void puntoCinco(); Se encarga de todas las “subfunciones”.
    •      void palabrasYFrecuencias(nodoA *arbol, int idArchivo, pyf *palabrasFrecuencias, int *validos) : Recorre el arbol de manera recursiva y carga un array con todas las palabras y su frecuencia en un documento.
    •      void sumaIdDoc(nodoT *lista, int id) : Retorna la frecuencia de una palabra según su ID.

6.
 
                void puntoSeis(); Se encarga de todas las “subfunciones”.
    •      int Levenshtein(char *s1, char *s2) : Función dada. Calcula la distancia de dos palabras.
    •      void buscarPalabrasSimilares(nodoA *arbol, char *palabra) : Imprime sugerencias para una palabra.
 
Librería interfaz:

    •      int menu(); : Retorna la opcion del menu -> funcioneMenu utiliza el retorno para el switch
    •      void funcionesMenu(termino *arr, int *validos, nodoA **arbol) : Función que se le pasa al main, se encarga de toda la lógica.
    •      void animation();
    •      void marcoConsola();
    •      void cargandoError();
    •      void logo();
    •      void copy();
