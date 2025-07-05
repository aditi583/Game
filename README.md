# Game
#include <stdio.h>
<br>
int main()
<br>
{
<br>
    char matrix[3][3];
    <br>
    int i, j;
<br>
    for (i = 0; i < 3; i++) 
    <br>
    {
    <br>
        for (j = 0; j < 3; j++)
        <br>
        {
          <br>
            matrix[i][j] = ' ';
        <br>
        }
        <br>
    }
<br>
    
   while (1)
   <br>
   {
   <br>
       int row, col;
      <br>
       char ch;
<br>
        printf("\nCurrent Matrix:\n");
    <br>
        for (i = 0; i < 3; i++)
        <br>
        {
        <br>
            for (j = 0; j < 3; j++) 
            <br>
            {
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
        printf("\nEnter the Position : ");
        <br>
        scanf("%d %d", &row, &col);
        <br>
        if (matrix[row][col] != ' ')
        <br>
        {
        <br>
            printf(" This position is already filled with '%c'\n", matrix[row][col]);
            <br>
            continue;
            <br>
        }
        <br>
        while (getchar() != '\n');
        <br>
        printf("Enter your string: ");
        <br>
        scanf("%c", &ch);
        <br>
        if (ch != 'x' && ch != 'o')
        <br>
        {
        <br>
            printf("\n ....Game only accept 'x' & 'o' Charecter....");
            <br>
            continue;
            <br>
        }
        <br>
        matrix[row][col] = ch;
        <br>
    }
    <br>
    return 0;
    <br>
}
<br>
