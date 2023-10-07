# cevrecilik.py
import discord
from discord.ext import commands
from settings import settings

intents = discord.Intents.default()
intents.message_content = True

# Botunuzu oluşturun
bot = commands.Bot(command_prefix='', intents=intents)

# Yardi
# m komutunu oluşturun
@bot.command()
async def yardim(ctx):
    yardim_mesaji = """
    Merhaba! Ben çevre dostu bir Discord botuyum. İşte kullanabileceğiniz komutlar:
    
    bilgi - Çevre temizliği ve hakkinda yeni şeyler öğrenmesize yardimci olur.
    geri donusum - Geri dönüşüm hakkinda yeni şeyler öğrenin.
    tasarruf - Enerji tasarrufu için yeni öneriler alin.
    """
    await ctx.send(yardim_mesaji)

# Bilgi komutunu oluşturun
@bot.command()
async def bilgi(ctx):
    bilgi_mesaji = "https://tr.wikipedia.org/wiki/%C3%87evrecilik#:~:text=%C3%87evrecilik%2C%20%C3%A7evre%20hareketini%20destekleme%20veya,aray%C4%B1%C5%9F%C4%B1nda%20olan%20sosyal%20bir%20harekettir."
    await ctx.send(bilgi_mesaji)

# Geri dönüşüm komutunu oluşturun
@bot.command()
async def geri_donusum(ctx):
    geri_donusum_mesaji = "Kullanilan malzemelerin yeniden kullanilabilecek hale getirilmesine "geri dönüşüm" adi verilir. Dünyanin geleceği ve doğanin korunmasi için geri dönüştürülmüş ve geri dönüştürülebilir materyaller ile üretilmiş ürünler tercih edilmelidir.

Geri Dönüşüm Hakkinda Bilgiler
Cam, kağit, karton, plastik gibi maddeler kendi içlerinde geri dönüştürülebilir. Bunun anlami temizlenip, işlenip yeniden ham madde haline gelebilir ve yeni ürünlerin üretilmesinde kullanilabilirler.
Geri dönüştürülmüş ürünler ile yeni ürünler üretilebilir. Örneğin bir deterjan kutusu geri dönüştürülmüş plastikten üretilebilir.
Geri dönüştürülmüş ürünler yeni ürünlerin üretilmesini ve kaynaklarin tüketilmesini gerektirmediği için daha sağliklidir. Özellikle çok da gerekli olmayan, tek sefer kullanilacak ürünler geri dönüştürülmüş ürünlerden seçilmelidir.
Geri dönüşümün de enerji ve su harcadiği unutulmamalidir. Geri dönüşümden bile daha etkili bir doğayi koruma tekniği bir şeyi almadan önce uzun uzun düşünmek ve gerçekten ihtiyacimiz varsa almak, sirf malzemeler geri dönüştürülebiliyor diye gereksiz alışveriş yapmamaktır.."
    await ctx.send(geri_donusum_mesaji)

# Enerji tasarrufu komutunu oluşturun
@bot.command()
async def tasarruf(ctx):
    tasarruf_mesaji = "Tasarruf, kişinin elinde bulunan şeylerin kiymetini bilmesi; onlari müsrifçe harcamadan birikim sağlayabilmesi demektir. Tasarruf geleceğe karşi tedbir almaktir.

Her insanin belirli bir geliri bulunur. İnsanlar hayatlarini devam ettirebilmek için mutlaka birtakim harcamalar yaparlar. Ancak bugünün yarini da vardir ve yarinin ne getireceği belli olmaz. Bu nedenle yarinin kötü sürprizlerine karş, her zaman tedbirli olmak gerekir. Maddi tedbirin yolu tasarruftan geçer. İnsan gelirinin bir kısmını mutlaka zor günleri için bir kenarda biriktirmelidir. Eğer bunu yaparsa gelecekte karşılaşacağı kötü sürprizlerden fazla zarar görmeden kurtulabilir.

Tasarruf bir fidandir. Zamanla büyür ve yillar sonra meyve verir. Her zaman azar azar kenara konan birikimler yillar sonra bakildiğinda büyük miktarlara dönüşür. Bu birikimler kişinin zor zamaninda ona bir dayanak olur. Bu nedenle herkes zor günlerini düşünerek tasarruf yapmalidir.."
    await ctx.send(tasarruf_mesaji)

# Botunuzu çaliştirin
bot.run(settings["Token"])
