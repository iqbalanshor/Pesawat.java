# Pesawat.java
# PesawatTempur.java
public class PesawatTempur {

    private final String warna;
    private int ketinggian; 
    private int kecepatan; 
    private int energi; 
    private String arah;
    private static final int MAX_KECEPATAN = 900;
    private static final int MAX_KETINGGIAN = 10000; 

    public PesawatTempur(String warna) {
        this.warna = warna;
        this.ketinggian = 0;
        this.kecepatan = 0;
        this.energi = 100;
        this.arah = "Utara";
    }

    public void nyalakanMesin() {
        System.out.println("Mesin pesawat dinyalakan...");
    }

    public void terbang() {
        if (this.kecepatan > 0) {
            if (this.energi >= 10) { 
                this.energi -= 10; // 
                System.out.println("Pesawat terbang...");
            } else {
                System.out.println("Energi tidak cukup untuk terbang.");
            }
        } else {
            System.out.println("Pesawat harus memiliki kecepatan untuk terbang.");
        }
    }

    public void tambahKecepatan(int kecepatan) {
        this.kecepatan += kecepatan;
        if (this.kecepatan > MAX_KECEPATAN) {
            this.kecepatan = MAX_KECEPATAN; 
        }
        System.out.println("Kecepatan pesawat bertambah menjadi " + this.kecepatan + " km/jam");
    }

    public void kurangiKecepatan(int kecepatan) {
        this.kecepatan -= kecepatan;
        if (this.kecepatan < 0) {
            this.kecepatan = 0; 
        }
        System.out.println("Kecepatan pesawat berkurang menjadi " + this.kecepatan + " km/jam");
    }

    public void belok(String arah) {
        this.arah = arah;
        System.out.println("Pesawat berbelok ke arah " + this.arah);
    }

    public void turun() {
        if (this.ketinggian - 100 >= 0) {
            this.ketinggian -= 100;
            System.out.println("Pesawat turun ke ketinggian " + this.ketinggian + " meter");
        } else {
            System.out.println("Pesawat sudah berada di ketinggian minimum.");
        }
    }

    public void infoPesawat() {
        System.out.println("------------------------");
        System.out.println("Informasi Pesawat:");
        System.out.println("Warna: " + this.warna);
        System.out.println("Ketinggian: " + this.ketinggian + " meter");
        System.out.println("Kecepatan: " + this.kecepatan + " km/jam");
        System.out.println("Energi: " + this.energi + "%");
        System.out.println("Arah: " + this.arah);
        System.out.println("------------------------");
    }
}    
![Code 2](https://github.com/user-attachments/assets/27c30989-c328-492c-a31f-c3512142d1d1)

# Main.java
public class Main {
    public static void main(String[] args) {

        PesawatTempur pesawat = new PesawatTempur("Merah");
        pesawat.infoPesawat();
        pesawat.nyalakanMesin();
        pesawat.terbang();
        pesawat.tambahKecepatan(200);
        pesawat.kurangiKecepatan(100);
        pesawat.belok("Barat");
        pesawat.infoPesawat();
        pesawat.kurangiKecepatan(50);
        pesawat.turun();
        pesawat.infoPesawat();
    }    
}
![code main](https://github.com/user-attachments/assets/0f1e69d0-f876-42fd-b697-f932ccc9dd9f)

# Output
![Screenshot 2024-09-30 135539](https://github.com/user-attachments/assets/bd9a289b-1782-4cdf-ad44-057764cb4be9)
![Screenshot 2024-09-30 135553](https://github.com/user-attachments/assets/4bdcf3a6-120a-4ca2-9d2a-fbcdd81ccdea)
