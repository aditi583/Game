# Game
<br>
#include <stdio.h>
<br>
char matrix[3][3];
    <br>
void setupMatrix()
    <br>{
    <br>
for (int i = 0; i < 3; i++)
    <br>
    {
    <br>
        for (int j = 0; j < 3; j++)
            <br>
            {
         <br>
            matrix[i][j] = ' ';
<br>
    printf("\nCurrent Matrix:\n");
    <br>
            for (int i = 0; i < 3; i++) {
        <br>
                for (int j = 0; j < 3; j++) {
            <br>
                    if (matrix[i][j] == ' ')
           <br>
                    printf("null\t");
            <br>
                    else
                    <br>
                printf("%c\t", matrix[i][j]);
                    <br>
        }
                    <br>
        printf("\n");
                    <br>
    }
                    <br>
}
<br>

char checkWinner() {
<br>
    for (int i = 0; i < 3; i++) {
    <br>
        if (matrix[i][0] == matrix[i][1] && matrix[i][1] == matrix[i][2] && matrix[i][0] != ' ')
        <br>
            return matrix[i][0];
        <br>
        if (matrix[0][i] == matrix[1][i] && matrix[1][i] == matrix[2][i] && matrix[0][i] != ' ')
            <br>
            return matrix[0][i];
    }
    <br>

if (matrix[0][0] == matrix[1][1] && matrix[1][1] == matrix[2][2] && matrix[0][0] != ' ')
<br>
        return matrix[0][0];
    <br>
    if (matrix[0][2] == matrix[1][1] && matrix[1][1] == matrix[2][0] && matrix[0][2] != ' ')
        <br>
        return matrix[0][2];
<br>
    return ' ';
<br>
}
<br>


int main() {
<br>
    int row, col;
    <br>
    char ch;
    <br>
    int count = 0;
<br>
    setupMatrix();  
<br>
    while (1) {
    <br>
        printf("\nEnter position : ");
       <br>
        scanf("%d %d", &row, &col);
<br>
        if (row < 0 || row > 2 || col < 0 || col > 2) {
    <br>
            printf("Invalid position! Try again.\n");
        <br>
            continue;
        <br>
        }
        <br>
        if (matrix[row][col] != ' ') {
           <br>
            printf("Position already filled with '%c'. Try again.\n", matrix[row][col]);
            <br>
            continue;
        <br>
        }
<br>
        printf("Enter the string: ");
        <br>
        while (getchar() != '\n'); 
        <br>
        scanf("%c", &ch);
<br>
        if (ch != 'x' && ch != 'o') {
    <br>
            printf("....Game only accept x and o charecter.....\n");
        <br>
        continue;
        <br>
        }
<br>
        matrix[row][col] = ch;
       <br>
        count++;
<br>
        printf("\n");
       <br>
        for (int i = 0; i < 3; i++) {
           <br>
            for (int j = 0; j < 3; j++) {
                <br>
                if (matrix[i][j] == ' ')
                    <br>
                    printf("null\t");
                <br>
                else
                    <br>
                    printf("%c\t", matrix[i][j]);
            <br>
            }
            <br>
            printf("\n");
        <br>
        }
<br>
        char winner = checkWinner();
        <br>
        if (winner == 'x' || winner == 'o') {
            <br>
            printf("\nPlayer '%c' wins!\n", winner);
            <br>
            break;
        }
<br>
        if (count == 9) {
    <br>
            printf("\nIt's a draw!\n");
        <br>
            break;
        }
        <br>
    }

    return 0;
}
