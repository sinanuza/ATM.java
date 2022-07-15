# ATM.java
www.patika.dev ATM uygulamasi



        import java.util.Scanner;

        public class banka_uygulamasi {
        public static void main(String[] args) {
        String password;
        String username;
        int balance = 0;
        int right = 3;
        int select;
        int tutar;

        while (right > 0) {
            System.out.println("Lutfen kullanici adinizi giriniz:");
            Scanner input = new Scanner(System.in);
            username = input.nextLine();
            System.out.println("Lutfen sifrenizi giriniz:");
            password = input.nextLine();
                if (username.equals("sinan") && (password.equals("1234")) ){
                System.out.println("Merhaba; XXX bankasina hosgeldiniz:");
                do {
                    System.out.println("Lutfen yapmak istediginiz islemi seciniz:");
                    System.out.println("1-Para Yatirma:\n" +
                            "2-Para Cekme:\n" +
                            "3-Bakiye Sorgulama\n" +
                            "4-CIKIS");
                    select=input.nextInt();
                    switch (select){
                        case 1:
                            System.out.println("Bakiyeniz:" + balance);
                            System.out.println("Lutfen cekmek isteginiz tutari giriniz:");
                            tutar=input.nextInt();
                            if (tutar>balance){
                                System.out.println("Bakiye yetersiz!");
                            }else {
                                balance -= tutar;
                                System.out.println("Kalan Bakiye:" + balance);
                            }
                            break;
                        case 2:
                            System.out.println("Bakiyeniz:" + balance);
                            System.out.println("Lutfen yatirmak isteginiz tutari giriniz:");
                            tutar=input.nextInt();
                            balance+=tutar;
                            System.out.println("Bakiyeniz:" + balance);
                            break;
                        case 3:
                            System.out.println("Bakiyeniz:" + balance);
                            break;
                        case 4:
                            System.out.println("Isleminiz sonlandirilmistir, iyi gunler dileriz.");
                            break;
                    }
                }while (select!=4);
                break;
            }else {
                    right--;
                    System.out.println("Hatali kullanici adi veya sifre lutfen tekrar deneyiniz:");
                    System.out.println("Kalan hakkiniz: "+right);
                    if (right==0){
                        System.out.println("Hesabiniz BLOKE olmustur, Lutfen banka ile iletisime geciniz");
                    }
                }
        }
    }
}
