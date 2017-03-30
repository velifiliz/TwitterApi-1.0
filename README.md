<snippet>
  <content><![CDATA[
# ${1:Project Name}

.NET ile Yazdığınız Projelerinizde Twitter İşlemlerinizi Yapmak İçin Kullanabileceğiniz Twitter Api'si.

## Kurulum

İndirdiğiniz Twitter Dll Dosyasını Projenize Dahil Ediniz.

## Kullanım

Öncelikle Twitter https://apps.twitter.com/ Sayfasından Yapacağınız İşlemler İçin Uygulama Oluşturunuz. Uygulamayı Oluşturduktan Sonra Bize Lazım Olan AccessToken,AccessTokenSecret,ConsumerKey,ConsumerSecret Karşılığına Denk Gelen Değerleri Projemizde Kullanmak Üzere Hazırlayınız.

Kütüphanemizde 3 Adet Metod Bulunmaktadır.

1.Metod Twitlerinizi JSON Türünde Geriye Döndürür.

            plugin.twitter t = new plugin.twitter();
            t.AccessToken = "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX";
            t.AccessTokenSecret = "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX";
            t.ConsumerKey = "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX";
            t.ConsumerSecret = "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX";
            string a = t.TweetList(t);
            MessageBox.Show(a);

2.Metod Tweet Paylaşmanızı Sağlar.

            plugin.twitter t = new plugin.twitter();
            t.AccessToken = "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX";
            t.AccessTokenSecret = "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX";
            t.ConsumerKey = "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX";
            t.ConsumerSecret = "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX";
            t.TweetShared("Merhaba Dünya",t); // tabi burda 140 karakteri unutmayınız.
            
3.Metod Tweet ve Fotoğraf Paylaşmamızı Sağlar.

            plugin.twitter t = new plugin.twitter();
            t.AccessToken = "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX";
            t.AccessTokenSecret = "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX";
            t.ConsumerKey = "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX";
            t.ConsumerSecret = "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX"; 
            byte[] img = File.ReadAllBytes("C:\\1.jpg"); // Windows Form
            //byte[] img = File.ReadAllBytes(Server.MapPath("~\\Images\\5.png")); // ASP.NET Web Form
            t.TweetPhoto(img, "Merhaba Dünya", t); 
            
## NOTLAR

1. Tweetlerinizi Projeniz Üzerinden Gönderirken 140 Karakter Kontrolü Yapmayı Unutmayın.
2. Twitterde Paylaşım Yapmak İçin Oluşturacağınız TwitterApp de Yazma İzni Vermeyi Unutmayın.
