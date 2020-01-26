package knight_tour;
import java.util.Scanner;



public class Knight_tour {
    static Scanner input = new Scanner(System.in);
    static int N = input.nextInt();
    
    
    
    public static void main(String[] args) {
        if(N < 10 && N > 4){
            solveKT();}
        else{
            System.out.println("the entered number must be between 4 & 10");
        }
    }

    
    
    /*check if next move lead to [0][0]
    so tour is closed
    */
    
    static boolean neighbour(int r, int c, int rr, int cc)  
    { 
        int[] xMove = {2, 1, -1, -2, -2, -1, 1, 2}; 
        int[] yMove = {1, 2, 2, 1, -1, -2, -2, -1};
        
        for (int i = 0; i < N; ++i) 
            if (((r + xMove[i]) == rr) &&  
                ((c + yMove[i]) == cc)) 
                return true; 
  
        return false; 
    } 
    
   /* A utility function to check if i,j are 
       valid indexes for N*N chessboard */
    static boolean isSafe(int r, int c, int chessboard [][]) { 
        return (r >= 0 && r < N && c >= 0 && c < N &&
                chessboard[r][c] == -1); 
    } 
  
        static void printSolution(int chessboard[][]) { 
        for (int r = 0; r < N; r++) { 
            for (int c = 0; c < N; c++) 
                System.out.print(chessboard[r][c] + " "); 
            System.out.println(); 
        } 
    } 
        
        
   /* This function solves the Knight Tour problem 
       using Backtracking.  This  function mainly 
       uses solveKTUtil() to solve the problem. It 
       returns false if no complete tour is possible, 
       otherwise return true and prints the tour. 
       Please note that there may be more than one 
       solutions, this function prints one of the 
       feasible solutions.  */
    static boolean solveKT() { 
        int[][] chessboard = new int[N][N]; 
  
         /* Initialization of solution matrix */
        for (int r = 0; r < N; r++) 
            for (int c = 0; c < N; c++) 
                chessboard[r][c] = -1; 
  
       /* xMove[] and yMove[] define next move of Knight. 
          xMove[] is for next value of x coordinate 
          yMove[] is for next value of y coordinate */
        int xMove[] = {2, 1, -1, -2, -2, -1, 1, 2}; 
        int yMove[] = {1, 2, 2, 1, -1, -2, -2, -1};
        
        // Since the Knight is initially at the first block
        chessboard[0][0] = 0;
        
        
        /* Start from 0,0 and explore all tours using 
           solveKTUtil() */
        if (!solveKTUtil(0, 0, 1, chessboard, xMove, yMove)) { 
            System.out.println("Solution does not exist"); 
            return false; 
        } else
            printSolution(chessboard); 
  
        return true; 
    } 
    
  /* A recursive utility function to solve Knight 
       Tour problem */
    static boolean solveKTUtil(int r, int c, int nextMove, int chessboard[][],
            int xMove[], int yMove[]) { 
        int k, next_r, next_c; 
        if (nextMove == N * N) 
            return true;
        
        /* Try all next moves from the current coordinate 
            x, y */
        for (k = 0; k < 8; k++) { 
            next_r = r + xMove[k]; 
            next_c = c + yMove[k]; 
            if (isSafe(next_r, next_c, chessboard)) { 
                chessboard[next_r][next_c] = nextMove; 
                if (solveKTUtil(next_r, next_c, nextMove + 1, chessboard, xMove,yMove))
                    return true; 
                
                else
                    chessboard[next_r][next_c] = -1;// backtracking 
            } 
        } 
  
        return false; 
    } 
}
