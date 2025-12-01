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
1. Auto-Lid Opening Simulation

If fill level < 80% → lid opens
If full → lid refuses to open
This simulates sensor-based lids.

2. Smell/Decomposition Sensor (Fake AI Logic)

If waste amount added many times → smell increases.
If smell > 70% → warning.

3. Time-Based Fill Simulation

Every second of delay increases smell or fill slightly.

4. Multi-Dustbin System (Wet + Dry)

User chooses:

Wet Bin

Dry Bin
Each fills separately.
