# Kata: Linked Lists - Push & BuildOneTwoThree

Objetivo:
Crear dos funciones para manejar listas enlazadas:

push(head, data): Añade un nodo con data al inicio de la lista.

buildOneTwoThree(): Construye y retorna la lista.

## 1 -> 2 -> 3 -> null

Explicación detallada:

1. Función push(head, data)
Propósito: Agregar un nuevo nodo al principio de la lista.

Mecánica:

Crea un nuevo nodo con data.

Su next apunta al nodo actual (head).

Retorna el nuevo nodo (que ahora es la cabeza de la lista).

Ejemplo:

      public static Node push(Node head, int data) {
          Node newNode = new Node(data); // Crear nuevo nodo
          newNode.next = head;           // Enlazar nuevo nodo al inicio
          return newNode;                // Retornar el nuevo nodo como cabeza
      }
      
Propósito: Construir la lista 1 -> 2 -> 3 usando push().

Clave:

Usar push en orden inverso porque cada nuevo nodo se añade al inicio.

Pasos:

Crea el nodo 3 sobre una lista vacía.

Añade 2 al inicio (lista: 2 -> 3).

Añade 1 al inicio (lista: 1 -> 2 -> 3).

Implementación:

    public static Node buildOneTwoThree() {
        Node head = null;          // Lista vacía
        head = push(head, 3);      // 3 -> null
        head = push(head, 2);      // 2 -> 3 -> null
        head = push(head, 1);      // 1 -> 2 -> 3 -> null
        return head;               // Retornar la lista
    }

    public class Main {
    public static void main(String[] args) {
        Node lista = buildOneTwoThree(); // Crear lista 1 -> 2 -> 3
        
        // Imprimir la lista
        Node current = lista;
        while (current != null) {
            System.out.print(current.data + " -> ");
            current = current.next;
        }
        System.out.println("null");
    }
}
Errores comunes:

Orden incorrecto: Si usas push(1), luego push(2), obtendrías 2 -> 1 -> 3.

Olvidar retornar el nuevo nodo en push().
