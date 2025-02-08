# dogum-rihi-hesaplama
veri yapıları ve algoritmalar dersi ödevi

#include <stdio.h>
#include <time.h>

int main() {
    struct tm dogum_tarihi = {0}; 
    time_t epoch_dogum, epoch_simdi;
    
    printf("dogum tarihi giriniz (YYYYY AA GG): ");
     scanf("%d %d %d", &dogum_tarihi.tm_year, &dogum_tarihi.tm_mon, &dogum_tarihi.tm_mday);
    
    dogum_tarihi.tm_year-=1900;
    dogum_tarihi.tm_mon-=1;
    
     epoch_dogum = mktime(&dogum_tarihi);
    epoch_simdi = time(NULL);
    
    time_t fark= epoch_simdi-epoch_dogum;
    
    printf("yasaginiz toplam gün %ld gun \n",fark / 86400);
   
   
   
    return 0;
}
