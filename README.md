actor PsikolojikZamanAnalizoru {

  stable var hucre : Int = 0; // Zaman değeri (hücre) saklanır

  // Zaman perspektifini hesaplamak için fonksiyon
  public func zamanHesaplama(yil : Int) : async Text {
    if (yil < 2024) {
      hucre := yil; // Geçmiş için yıl değeri saklanır
      return "Geçmiş";
    } else if (yil == 2024) {
      hucre := yil; // Şu an için yıl değeri saklanır
      return "Şu An";
    } else {
      hucre := yil; // Gelecek için yıl değeri saklanır
      return "Gelecek";
    }
  };

  // Kullanıcının zaman perspektifini değiştiren ve kaydeden fonksiyon
  public func zamanDegistir(yil : Int) : async () {
    let zamanDurumu = await zamanHesaplama(yil);
    // Burada kullanıcıya mesaj gösterilebilir veya veri kaydedilebilir
    // Örneğin, zaman durumu ile hucre değeri kaydedilebilir
  };

  // Zaman hücresine değer eklemek için fonksiyon (toplama)
  public func zamanTopla(deger : Int) : async () {
    hucre := hucre + deger; // Zaman hücresine değer eklenir
  };

  // Zaman hücresinden değer çıkarmak için fonksiyon (çıkarma)
  public func zamanCikar(deger : Int) : async () {
    hucre := hucre - deger; // Zaman hücresinden değer çıkarılır
  };

  // Zaman hücresinin değerini almak için fonksiyon
  public query func getZamanDurumu() : async Int {
    return hucre; // Mevcut zaman değeri döndürülür
  };

};
