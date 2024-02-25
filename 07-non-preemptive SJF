#include <stdio.h>
struct Process {
    int pid;
    int arrival_time;
    int burst_time;
};
void sort_by_arrival(struct Process pro[], int n) {
    for (int i = 0; i < n - 1; i++) {
        for (int j = 0; j < n - i - 1; j++) {
            if (pro[j].arrival_time > pro[j + 1].arrival_time) {
                struct Process temp = pro[j];
                pro[j] = pro[j + 1];
                pro[j + 1] = temp;
            }
        }
    }
}
void calculate_times(struct Process pro[], int n) {
    int wait_time = 0;
    int turnaround_time = 0;
    for (int i = 0; i < n; i++) {
        turnaround_time += pro[i].burst_time;
        pro[i].burst_time = turnaround_time;
        wait_time += pro[i].burst_time - pro[i].arrival_time;
    }
    printf("Process\tArrival Time\tBurst Time\tWaiting Time\tTurnaround Time\n");
    for (int i = 0; i < n; i++) {
        printf("P[%d]\t%d\t\t%d\t\t%d\t\t%d\n", pro[i].pid, pro[i].arrival_time,
               pro[i].burst_time, wait_time, pro[i].burst_time);
    }
    double avg_wait_time = (double)wait_time / n;
    double avg_turnaround_time = (double)turnaround_time / n;
    printf("\nAverage Waiting Time: %.2lf\n", avg_wait_time);
    printf("Average Turnaround Time: %.2lf\n", avg_turnaround_time);
}
int main() {
    int n;
    printf("Enter the number of processes: ");
    scanf("%d", &n);
    struct Process pro[n];
    for (int i = 0; i < n; i++) {
        printf("Enter arrival time of process P[%d]: ", i + 1);
        scanf("%d", &pro[i].arrival_time);
        pro[i].pid = i + 1;
    }
    for (int i = 0; i < n; i++) {
        printf("Enter burst time of process P[%d]: ", i + 1);
        scanf("%d", &pro[i].burst_time);
    }
    sort_by_arrival(pro, n);
    calculate_times(pro, n);
    return 0;
}
