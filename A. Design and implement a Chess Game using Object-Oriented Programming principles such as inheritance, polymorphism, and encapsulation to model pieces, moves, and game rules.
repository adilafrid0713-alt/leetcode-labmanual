import java.util.Scanner;

// Encapsulation: Hiding internal state of coordinates
class Position {
    private int x, y;
    public Position(int x, int y) { this.x = x; this.y = y; }
    public int getX() { return x; }
    public int getY() { return y; }
}

// Inheritance: Base abstract class for all pieces
abstract class Piece {
    protected boolean isWhite; // Encapsulated color
    public Piece(boolean isWhite) { this.isWhite = isWhite; }
    public boolean isWhite() { return isWhite; }
    
    // Polymorphism: Each subclass defines its own move rules
    public abstract boolean isValidMove(Position start, Position end);
    public abstract String getSymbol();
}

// Subclass: Pawn
class Pawn extends Piece {
    public Pawn(boolean isWhite) { super(isWhite); }

    @Override
    public boolean isValidMove(Position start, Position end) {
        int direction = isWhite ? -1 : 1;
        // Basic one-step forward logic for demonstration
        return start.getY() == end.getY() && (end.getX() - start.getX()) == direction;
    }

    @Override
    public String getSymbol() { return isWhite ? "WP" : "BP"; }
}

// Subclass: King
class King extends Piece {
    public King(boolean isWhite) { super(isWhite); }

    @Override
    public boolean isValidMove(Position start, Position end) {
        return Math.abs(start.getX() - end.getX()) <= 1 && Math.abs(start.getY() - end.getY()) <= 1;
    }

    @Override
    public String getSymbol() { return isWhite ? "WK" : "BK"; }
}

// The Game Board
public class ChessGameOOP {
    private Piece[][] board = new Piece[8][8];

    public ChessGameOOP() {
        initializeBoard();
    }

    private void initializeBoard() {
        // Place a few pieces for demonstration
        board[1][0] = new Pawn(false); // Black Pawn
        board[6][0] = new Pawn(true);  // White Pawn
        board[7][4] = new King(true);  // White King
        board[0][4] = new King(false); // Black King
    }

    public void displayBoard() {
        System.out.println("\n  0  1  2  3  4  5  6  7");
        for (int i = 0; i < 8; i++) {
            System.out.print(i + " ");
            for (int j = 0; j < 8; j++) {
                if (board[i][j] == null) System.out.print("-- ");
                else System.out.print(board[i][j].getSymbol() + " ");
            }
            System.out.println();
        }
    }

    public void movePiece(int startX, int startY, int endX, int endY) {
        Piece piece = board[startX][startY];
        if (piece == null) {
            System.out.println("No piece at starting position.");
            return;
        }

        Position start = new Position(startX, startY);
        Position end = new Position(endX, endY);

        // Polymorphic call to isValidMove
        if (piece.isValidMove(start, end)) {
            board[endX][endY] = piece;
            board[startX][startY] = null;
            System.out.println("Move successful.");
        } else {
            System.out.println("Invalid move for this piece.");
        }
    }

    public static void main(String[] args) {
        ChessGameOOP game = new ChessGameOOP();
        System.out.println("Chess OOP Initialized!");
        game.displayBoard();
        
        System.out.println("\nMoving White Pawn from (6,0) to (5,0)...");
        game.movePiece(6, 0, 5, 0);
        game.displayBoard();
    }
}
