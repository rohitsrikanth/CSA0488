#include <stdio.h>
struct Process {
    int pid;
    int burst_time;
    int priority;
};
bool compare(Process a, Process b) {
    return (a.priority > b.priority);
}
void waitingtime(Process pro[], int n, int wt[]) {
    wt[0] = 0;
    for (int i = 1; i < n; i++) {
        wt[i] = pro[i - 1].burst_time + wt[i - 1];
    }
}
void turnaround(Process pro[], int n, int wt[], int tat[]) {
    for (int i = 0; i < n; i++) {
        tat[i] = pro[i].burst_time + wt[i];
    }
}
void avgtime(Process pro[], int n) {
    int wt[n], tat[n], total_wt = 0, total_tat = 0;
    waitingtime(pro, n, wt);
    turnaround(pro, n, wt, tat);
    printf("Processes\tBurst time\tWaiting time\tTurnaround time\n");
    for (int i = 0; i < n; i++) {
        printf("P[%d]\t\t%d\t\t%d\t\t%d\n", pro[i].pid, pro[i].burst_time, wt[i], tat[i]);
        total_wt += wt[i];
        total_tat += tat[i];
    }
    printf("\nAverage Waiting Time = %lf\n", (double)total_wt / n);
    printf("Average Turnaround Time = %lf\n", (double)total_tat / n);
}
int main() {
    int n;
    printf("Enter the number of processes: ");
    scanf("%d", &n);
    Process pro[n];
    for (int i = 0; i < n; i++) {
        printf("Enter arrival time of process P[%d]: ", i + 1);
        scanf("%d", &pro[i].burst_time);
    }
    for (int i = 0; i < n; i++) {
        printf("Enter burst time of process P[%d]: ", i + 1);
        scanf("%d", &pro[i].burst_time);
    }
    for (int i = 0; i < n; i++) {
        printf("Enter priority of process P[%d]: ", i + 1);
        scanf("%d", &pro[i].priority);
    }
    avgtime(pro, n);
    return 0;
}
