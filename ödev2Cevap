#include <stdio.h>
#define N 4                         //sabit matris
#define M 3                         // filtre matris
#define K (N - M + 1)               // görüntü matrisi

void toplam(int sabitdizi[N][N], int degiskendizi[M][M], int carp[K][K]);

int main() {
    int sabitdizi[N][N], degiskendizi[M][M], carp[K][K] = {0};
    int i, b;
    int sabitDegerleri, degiskeninDegerleri;
    int sayac = 1;

    printf("Sabit matrisinize eklemek istediginiz degerleri giriniz:\n");
    for (i = 0; i < N; i++) {
        for (b = 0; b < N; b++) {
            printf("%d. degerinizi giriniz: ", sayac);
            sayac++;
            scanf("%d", &sabitDegerleri);
            sabitdizi[i][b] = sabitDegerleri;
        }
    }

    printf("Filtrenize eklemek istediginiz degerleri giriniz:\n");
    sayac = 1;
    for (i = 0; i < M; i++) {
        for (b = 0; b < M; b++) {
            printf("%d. degerinizi giriniz: ", sayac);
            sayac++;
            scanf("%d", &degiskeninDegerleri);
            degiskendizi[i][b] = degiskeninDegerleri;
        }
    }

    
    toplam(sabitdizi, degiskendizi, carp);

    return 0;
}

void toplam(int sabitdizi[N][N], int degiskendizi[M][M], int carp[K][K]) {
    int i, b, x, y;
    int filtreToplam = 0, toplam;

                    // Filtre elemanlarının toplamını hesapla
    for (i = 0; i < M; i++) {
        for (b = 0; b < M; b++) {
            filtreToplam += degiskendizi[i][b];
        }
    }

                    // Filtre toplamı sıfırsa hata mesajı çünkü payda 0 olamaz
    if (filtreToplam == 0) {
        printf("Filtre elemanlarinin toplami 0 olamaz.\n");
        return;
    }

   // Konvolüsyon işlemi
    for (i = 0; i <= N - M; i++) {
        for (b = 0; b <= N - M; b++) {
            toplam = 0; 
            for (x = 0; x < M; x++) {
                for (y = 0; y < M; y++) {
                    toplam += sabitdizi[i + x][b + y] * degiskendizi[x][y];
                }
            }
            carp[i][b] = toplam / filtreToplam; 
        }
    }

                    // görüntü matrisi yazdırılır
    printf("Sonuc matrisi:\n");
    for (i = 0; i < K; i++) {
        for (b = 0; b < K; b++) {
            printf("%d\t", carp[i][b]);
        }
        printf("\n");
    }
}
