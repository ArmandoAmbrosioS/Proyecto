# Proyecto
Proyecto final programacion 3 

//
System.out.println("Hola mundo")

public class ListaEnlazada {

    private Nodo nodoInicio;
    private int tamanio;

    public ListaEnlazada() {
        this.nodoInicio = null;
        this.tamanio = 0;
    }

    public boolean estaVacia() {
        if (this.tamanio == 0 && nodoInicio == null) {
            return true;
        } else {
            return false;
        }
    }

    public void agregar(Nodo nodo) {
        if (estaVacia()) {
            nodoInicio = nodo;
            tamanio++;
        } else {
            Nodo nodoAuxiliar = nodoInicio;
            for (int i = 0; i < tamanio - 1; i++) {
                nodoAuxiliar = nodoAuxiliar.obtenerSiguiente();
            }
            nodoAuxiliar.enlazarSiguiente(nodo);
            tamanio++;
        }
    }

    public void imprimirLista() {
        System.out.println("Lista");
        Nodo nodoAuxiliar = nodoInicio;
        for (int i = 0; i < tamanio - 1; i++) {
            System.out.println(nodoAuxiliar.toString());
            nodoAuxiliar = nodoAuxiliar.obtenerSiguiente();
        }
    }

    public void agregarInicio(Nodo nodo) {
        if (estaVacia()) {
            nodoInicio = nodo;
        }else{
            nodo.enlazarSiguiente(nodoInicio);
            nodoInicio=nodo;
        }
        tamanio++;
    }
    public void agregarFinal(Nodo nodo){
        Nodo nodoAux=nodoInicio;
        for (int i = 0; i < tamanio-1; i++) {
            nodoAux=nodoAux.obtenerSiguiente();
        }
        nodoAux.enlazarSiguiente(nodo);
        tamanio++;
        
    }
    public void eliminarInicio(){
        Nodo nodoAux=nodoInicio.obtenerSiguiente();
        nodoInicio=nodoAux;
        tamanio--;
    }
    public void eliminarFinal(){
        Nodo nodoAux=nodoInicio;
        for (int i = 0; i < tamanio-2; i++) {
            nodoAux=nodoAux.obtenerSiguiente();
        }
        nodoAux.enlazarSiguiente(null);
        tamanio--;
    }
    public void actualizar(int pos, Nodo nodo){
        Nodo nodoAux = nodoInicio;
        Nodo nodoAux2= null;
        for (int i = 0; i < pos-1; i++) {
            nodoAux=nodoAux.obtenerSiguiente();
        }
        nodoAux2=nodoAux.obtenerSiguiente();
        nodoAux2=nodoAux2.obtenerSiguiente();
        nodoAux.enlazarSiguiente(nodo);
        nodoAux=nodoAux.obtenerSiguiente();
        nodoAux.enlazarSiguiente(nodoAux2);
     
     
    }
}
