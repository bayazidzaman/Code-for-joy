#include <stdio.h>
#include <ctype.h>
#include <string.h>

void analyze(char *input) {
    int i = 0;
    int lines = 1;
    char identifiers[100][100];
    char operators[100];
    int id_count = 0, op_count = 0;

    printf("The no’s in the program are:\n");

    printf("The keywords and identifiers are:\n");
    while (input[i] != '\0') {
        if (isalpha(input[i])) {
            // If it's an alphabet, it could be an identifier
            char id[100];
            int j = 0;
            while (isalpha(input[i]) || isdigit(input[i])) {
                id[j++] = input[i++];
            }
            id[j] = '\0';
            strcpy(identifiers[id_count++], id);
            printf("%s is an identifier and terminal\n", id);
        } else if (isdigit(input[i])) {
            // If it's a digit, it could be part of a number
            while (isdigit(input[i])) {
                i++;
            }
        } else if (input[i] == '+' || input[i] == '*' || input[i] == '-' || input[i] == '/' || input[i] == '=') {
            // Operators
            operators[op_count++] = input[i++];
        } else if (input[i] == '\n') {
            lines++;
            i++;
        } else if (input[i] == ' ' || input[i] == '\t') {
            // Skip whitespaces and tabs
            i++;
        } else {
            i++;
        }
    }

    // Print special characters (operators)
    printf("Special characters are:\n");
    for (int k = 0; k < op_count; k++) {
        printf("%c ", operators[k]);
    }
    printf("\n");

    printf("Total no. of lines are: %d\n", lines);
}

int main() {
    char input[1000];

    printf("Enter the C program: ");
    fgets(input, 1000, stdin);

    // Remove the newline character at the end if it exists
    size_t len = strlen(input);
    if (len > 0 && input[len - 1] == '\n') {
        input[len - 1] = '\0';
    }

    analyze(input);

    return 0;
}
