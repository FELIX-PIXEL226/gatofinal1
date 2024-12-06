# gatofinal1
Practica de NeatBeans subida a GITHUB

package com.mycompany.gatofinal1;
// Diego francisco Felix Garza 

// Este codigo recrea el juego del gato con matrices aparte de agregar una proyeccionde 
//una imagen al ganador 
import java.util.Scanner;
import javax.swing.*; // Importar librerías para mostrar imágenes

public class Gatofinal1 {
    public static void main(String[] args) {
        char[][] tablero = {
            {' ', ' ', ' '},
            {' ', ' ', ' '},
            {' ', ' ', ' '}
        };

        Scanner scanner = new Scanner(System.in);
        boolean turnoX = true; // Verdadero para "X", falso para "O"
        boolean juegoEnCurso = true;

        while (juegoEnCurso) {
            imprimirTablero(tablero);
            System.out.println("Turno de " + (turnoX ? "X" : "O"));
            System.out.print("Ingresa fila (0, 1, 2): ");
            int fila = scanner.nextInt();
            System.out.print("Ingresa columna (0, 1, 2): ");
            int columna = scanner.nextInt();

            // Validar la posición
            if (fila < 0 || fila > 2 || columna < 0 || columna > 2 || tablero[fila][columna] != ' ') {
                System.out.println("Movimiento inválido. Intenta de nuevo.");
                continue;
            }

            // Colocar "X" o "O" en el tablero
            tablero[fila][columna] = turnoX ? 'X' : 'O';

            // Verificar si hay un ganador
            if (verificarGanador(tablero, turnoX ? 'X' : 'O')) {
                imprimirTablero(tablero);
                System.out.println("¡El jugador " + (turnoX ? "X" : "O") + " ha ganado!");
                mostrarImagen(); // Llamada al método para mostrar la imagen
                juegoEnCurso = false;
            } else if (tableroLleno(tablero)) {
                imprimirTablero(tablero);
                System.out.println("¡Empate!");
                juegoEnCurso = false;
            } else {
                turnoX = !turnoX; // Cambiar turno
            }
        }
    }

    private static void imprimirTablero(char[][] tablero) {
        System.out.println("  0   1   2");
        for (int i = 0; i < 3; i++) {
            System.out.println(" " + tablero[i][0] + " | " + tablero[i][1] + " | " + tablero[i][2]);
            if (i < 2) {
                System.out.println("---|---|---");
            }
        }
    }

    private static boolean verificarGanador(char[][] tablero, char simbolo) {
        // Verificar filas y columnas
        for (int i = 0; i < 3; i++) {
            if ((tablero[i][0] == simbolo && tablero[i][1] == simbolo && tablero[i][2] == simbolo) ||
                (tablero[0][i] == simbolo && tablero[1][i] == simbolo && tablero[2][i] == simbolo)) {
                return true;
            }
        }

        // Verificar diagonales
        if ((tablero[0][0] == simbolo && tablero[1][1] == simbolo && tablero[2][2] == simbolo) ||
            (tablero[0][2] == simbolo && tablero[1][1] == simbolo && tablero[2][0] == simbolo)) {
            return true;
        }

        return false;
    }

    private static boolean tableroLleno(char[][] tablero) {
        for (int i = 0; i < 3; i++) {
            for (int j = 0; j < 3; j++) {
                if (tablero[i][j] == ' ') {
                    return false;
                }
            }
        }
        return true;
    }

    private static void mostrarImagen() {
        // Ruta de la imagen
        String rutaImagen = "C:/Users/DELL/Downloads/ganasterei1.jpg";

        // Crear un marco para mostrar la imagen
        JFrame frame = new JFrame("Ganador");
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setSize(400, 400); // Tamaño del marco

        // Cargar la imagen usando la ruta proporcionada
        ImageIcon icon = new ImageIcon(rutaImagen);
        JLabel label = new JLabel(icon);

        // Agregar la imagen al marco
        frame.add(label);
        frame.setVisible(true);
    }
}
