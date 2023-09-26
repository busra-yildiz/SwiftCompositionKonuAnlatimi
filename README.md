# SwiftCompositionKonuAnlatimi
 Swift programlama dilinde "composition" (bileşim), bir nesnenin başka nesneleri içinde barındırma ve bu nesneleri kullanma
 yeteneği anlamına gelir. Composition, nesneler arasında güçlü bir ilişki kurmanıza ve karmaşık işlevselliği daha küçük, yönetilebilir
 parçalara bölmeye olanak tanır. İşte Swift'te composition'ı nasıl kullanabileceğinizin bir özeti:

Temel Composition Örnekleri:

Nesne içinde nesne:
Bir sınıf, başka bir sınıfın örneğini içerebilir. Bu, başka bir nesnenin özelliklerini ve işlevselliğini kullanmanıza olanak tanır. Örnek:
class Motor {
    var devirSayisi: Int = 0
    func calistir() {
        print("Motor çalıştı.")
    }
}

class Araba {
    var marka: String = ""
    var motor: Motor = Motor()
    
    func hareketeGec() {
        motor.calistir()
        print("\(marka) arabası harekete geçti.")
    }
}

Bu örnekte, Araba sınıfı, bir Motor örneğini içerir. Araba, harekete geçtiğinde motor da çalıştırılır.
Protokol Kullanımı:
Composition, protokoller aracılığıyla da gerçekleştirilebilir. Bir sınıf, bir protokolü uygulayan bir başka sınıfın örneğini 
içerebilir. Bu, kodunuzu daha esnek hale getirir. Örnek:

protocol Surulebilir {
    func sur()
}

class TekerlekliAraclar: Surulebilir {
    func sur() {
        print("Tekerlekli araç sürülüyor.")
    }
}

class Araba {
    var tekerlekliArac: Surulebilir = TekerlekliAraclar()
    
    func hareketeGec() {
        tekerlekliArac.sur()
    }
}

Bu örnekte, Araba sınıfı, Surulebilir protokolünü uygulayan bir örneği içerir. 
Bu, farklı tekerlekli araç türlerini kullanabilmenizi sağlar.
Composition Avantajları:

Modülerlik: Composition, büyük ve karmaşık sınıfları daha küçük, yönetilebilir bileşenlere bölmeyi sağlar. 
Bu, kodunuzu daha anlaşılır ve bakımı daha kolay hale getirir.
Esneklik: Composition sayesinde nesnelerinizi dinamik olarak değiştirebilir veya farklı bileşenleri
bir araya getirerek farklı davranışlar elde edebilirsiniz.
Test Edebilirlik: Bir bileşenin bağımsız olarak test edilebilmesi, hataları tespit etmeyi ve düzeltmeyi
kolaylaştırır.
Daha Az Bağımlılık: Inheritance (kalıtım) yerine composition kullanmak, sınıflar arasındaki sıkı bağımlılıkları 
azaltabilir ve daha az kırılgan kod oluşturmanıza yardımcı olabilir.
Composition, Swift dilinde güçlü bir araçtır ve kodunuzun daha temiz, düzenli ve esnek olmasına yardımcı olabilir.
Composition kullanarak nesnelerinizi daha iyi düzenleyebilir ve karmaşık işlevselliği daha küçük parçalara bölebilirsiniz.




