# Tofu.kz
Shoes
import { Button } from "@/components/ui/button"; import { Card, CardContent } from "@/components/ui/card"; import { Input } from "@/components/ui/input"; import Image from "next/image";

export default function Home() { return ( <div className="flex flex-col items-center w-full text-center"> {/* Header */} <header className="w-full py-6 px-4 flex justify-between items-center shadow-md bg-white"> <h1 className="text-2xl font-bold text-mint-600">Tofu</h1> <nav className="space-x-4 text-sm"> <a href="#catalog">Каталог</a> <a href="#how">Как это работает</a> <a href="#reviews">Отзывы</a> <a href="#about">О нас</a> <a href="#delivery">Доставка</a> </nav> <div className="space-x-2"> <Button variant="outline">В корзину</Button> <Button>Купить</Button> </div> </header>

{/* Hero */}
  <section className="bg-mint-100 w-full py-16 px-4 flex flex-col items-center">
    <h2 className="text-4xl font-bold mb-4">Обувь, которая растёт вместе с вашим малышом</h2>
    <p className="mb-6 text-lg">Регулируемый размер: от 22 до 25</p>
    <Button size="lg">Выбрать модель</Button>
  </section>

  {/* How It Works */}
  <section id="how" className="py-16 px-4 w-full max-w-4xl">
    <h3 className="text-3xl font-semibold mb-8">Как работает Tofu</h3>
    <div className="grid grid-cols-1 md:grid-cols-3 gap-6">
      <Card>
        <CardContent className="p-6">
          <h4 className="font-semibold text-lg mb-2">1. Надень</h4>
          <p>Обувь легко надевается и фиксируется по стопе ребёнка.</p>
        </CardContent>
      </Card>
      <Card>
        <CardContent className="p-6">
          <h4 className="font-semibold text-lg mb-2">2. Отрегулируй</h4>
          <p>Регулировка размера происходит с помощью простого механизма.</p>
        </CardContent>
      </Card>
      <Card>
        <CardContent className="p-6">
          <h4 className="font-semibold text-lg mb-2">3. Носи до 4 сезонов</h4>
          <p>Надёжность и комфорт — на долгий срок.</p>
        </CardContent>
      </Card>
    </div>
    <Button className="mt-6">Смотреть видео</Button>
  </section>

  {/* Catalog */}
  <section id="catalog" className="py-16 px-4 w-full max-w-6xl">
    <h3 className="text-3xl font-semibold mb-8">Каталог моделей</h3>
    <div className="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-6">
      {[
        { name: "Tofu Breeze", size: "22–25", price: "18 900 ₸", image: "/shoes1.png" },
        { name: "Tofu Step", size: "21–24", price: "19 500 ₸", image: "/shoes2.png" },
        { name: "Tofu Winter", size: "23–26", price: "21 000 ₸", image: "/shoes3.png" },
      ].map((shoe, index) => (
        <Card key={index} className="overflow-hidden">
          <Image
            src={shoe.image}
            alt={shoe.name}
            width={300}
            height={200}
            className="w-full object-cover"
          />
          <CardContent className="p-4 text-left">
            <h4 className="text-lg font-semibold mb-1">{shoe.name}</h4>
            <p className="text-sm text-gray-600 mb-1">Размер: {shoe.size}</p>
            <p className="text-base font-bold mb-3">{shoe.price}</p>
            <Button className="w-full">Добавить в корзину</Button>
          </CardContent>
        </Card>
      ))}
    </div>
  </section>

  {/* Footer */}
  <footer className="w-full py-12 px-4 bg-gray-100 text-sm text-gray-600">
    <div className="max-w-4xl mx-auto grid grid-cols-1 md:grid-cols-3 gap-4">
      <div>
        <h5 className="font-bold mb-2">Контакты</h5>
        <p>Email: info@tofu.kz</p>
        <p>Instagram: @tofu.shoes</p>
      </div>
      <div>
        <h5 className="font-bold mb-2">Информация</h5>
        <p>Доставка и оплата</p>
        <p>Политика возврата</p>
      </div>
      <div>
        <h5 className="font-bold mb-2">Подписка</h5>
        <Input placeholder="Введите ваш email" />
        <Button className="mt-2">Подписаться</Button>
      </div>
    </div>
  </footer>
</div>

); }

