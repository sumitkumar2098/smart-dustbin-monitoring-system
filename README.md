#include <stdio.h>

int main() {
    int capacity = 100;      // Dustbin capacity in percentage
    int fill = 0;            // Current fill level
    int waste;

    printf("=== SMART DUSTBIN MONITORING SYSTEM ===\n");

    while (fill < capacity) {
        printf("\nEnter waste amount to add (0-20): ");
        scanf("%d", &waste);

        if (waste < 0 || waste > 20) {
            printf("Invalid input! Enter between 0-20.\n");
            continue;
        }

        fill += waste;

        if (fill > capacity)
            fill = capacity;

        printf("Dustbin Fill Level: %d%%\n", fill);

        if (fill >= 80 && fill < 100)
            printf("Warning: Dustbin almost full!\n");
        else if (fill == 100)
            printf("ALERT: Dustbin FULL! Please empty it.\n");
    }

    printf("\nSystem Stopped: Dustbin has reached full capacity.\n");

    return 0;
}
# smart-dustbin-monitoring-system
