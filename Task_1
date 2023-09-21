#include <stdio.h>
#include <string.h>
#include <stdlib.h>

#define MAX_STUDENTS 100

typedef struct {
    char name[50];
    char surname[50];
    char github_nickname[50];
    float average_score;
} Student;

Student students[MAX_STUDENTS];
int student_count = 0;

char *locale = "UA";

void clear_screen() {
    #ifdef _WIN32
    system("cls");
    #else
    system("clear");
    #endif
}

void show_student_info(Student s) {
    if (strcmp(locale, "UA") == 0) {
        printf("\n---- Інформація про студента ----\n");
        printf("Ім'я: %s\n", s.name);
        printf("Прізвище: %s\n", s.surname);
        printf("Нікнейм на GitHub: %s\n", s.github_nickname);
        printf("Середній бал: %.2f\n", s.average_score);
        printf("-------------------------------\n");
    } else {
        // ... other locales if needed
    }
}

void add_student() {
    if(student_count < MAX_STUDENTS) {
        if (strcmp(locale, "UA") == 0) {
            printf("Як звуть студента? ");
            scanf("%s", students[student_count].name);
        
            printf("Та прізвище? ");
            scanf("%s", students[student_count].surname);
        
            printf("Який у нього нік на GitHub? ");
            scanf("%s", students[student_count].github_nickname);
        
            printf("І, нарешті, який його середній бал? ");
            scanf("%f", &students[student_count].average_score);
        }
        
        student_count++;
    } else {
        printf("У вас вже максимальна кількість студентів!\n");
    }
}

void delete_student() {
    int index;
    if (strcmp(locale, "UA") == 0) {
        printf("Введіть номер студента, якого ви хочете видалити: ");
    }
    scanf("%d", &index);
    if(index < student_count && index >= 0) {
        for(int i = index; i < student_count - 1; i++) {
            students[i] = students[i+1];
        }
        student_count--;
        printf("Студент видалений!\n");
    } else {
        printf("Невірний номер студента!\n");
    }
}

void list_students() {
    printf("\nСписок студентів:\n");
    for(int i = 0; i < student_count; i++) {
        printf("%d. %s %s\n", i+1, students[i].name, students[i].surname);
    }
}

int main() {
    int choice;
    do {
        clear_screen();  // Очищаем экран
        
        if (strcmp(locale, "UA") == 0) {
            printf("\nМеню:\n");
            printf("1. Додати студента\n");
            printf("2. Видалити студента\n");
            printf("3. Перелічити всіх студентів\n");
            printf("4. Вихід\n");
            printf("Виберіть дію: ");
        }
        scanf("%d", &choice);

        switch(choice) {
            case 1:
                add_student();
                break;
            case 2:
                delete_student();
                break;
            case 3:
                list_students();
                break;
            case 4:
                printf("До побачення!\n");
                break;
            default:
                printf("Невірний вибір!\n");
        }
    } while(choice != 4);

    return 0;
}
