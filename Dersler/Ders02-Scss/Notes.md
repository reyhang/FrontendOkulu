# **SCSS NOTLARI**

## *@mixin ve @include Nedir?*

SCSS'de @include direktifi, daha önce tanımlanmış bir @mixin'i kullanarak, tekrar tekrar yazmak zorunda kalmadan aynı stil kurallarını birden çok yerde uygulamamıza yarar. Bu, özellikle kod tekrarını azaltmak ve stil kurallarını merkezi bir noktadan yönetmek için çok faydalıdır.

**@mixin:**
SCSS’de bir @mixin, belirli bir stil grubunu tanımlamak için kullanılır. Parametreler alabilir, böylece her çağrıldığında farklı değerlerle uygulanabilir.

**@include:**
 Bir @mixin’i uygulamak istediğimiz yerde @include ifadesini kullanırız. Böylece @mixin'de tanımlanan tüm kurallar, @include ile çağrıldığı yerde geçerli olur.

**Örnek:**

@mixin boxMixin($color, $width, $height) {
  width: $width;
  height: $height;
  background-color: $color;
  border: 1px solid darken($color, 20%);
  padding: 10px;
  margin: 5px;
}

.container {
  display: flex;

  .box1 {
    @include boxMixin(rgb(0, 247, 255), 150px, 100px);
  }

  .box2 {
    @include boxMixin(orange, 200px, 150px);
  }

  .box3 {
    @include boxMixin(green, 100px, 80px);
  }
}
