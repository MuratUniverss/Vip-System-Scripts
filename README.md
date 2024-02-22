# Vip-System-Scripts
quest vip_user begin
	state start begin
		when login with pc.getqf("vip") == 1 begin -- her oyuna girdiğinde alttan yazı geçer.
			if get_time() > pc.getqf("vipsure") then
				pc.setqf("vipsure",0)
				pc.setqf("vip",0)
				chat(pc . get_name ( ) .. " VIP üyeliğinin süresi doldu. ")
			else
				local kalansure = pc.getqf("vipsure")-get_time()
				local hesapla = math.floor(kalansure/60/60)
				chat(pc . get_name ( ) .. " VIP üyeliğin "..hesapla.." saat sonra bitecek. ")
			-- end
		end
		when login with pc.getqf("vip")==1 and not npc . is_pc ( )begin
		end
		when 81200.use with pc.getqf("vip")==0 begin --- Erkek
			vip_isim = pc.get_name()
			say_title("VIP Sistemi")
			say_color("yellow","S-Type2 VIP üyelik size bir çok şey kazandıracak,")
			say_color("yellow","Bunlardan biri isminin başına VIP eki gelmesidir.")
			say_color("yellow","Ek olarak sana bir çok özellik eklenecek.")
			say_color("yellow","Oyun içinde VIP Uyelere ozel kostüm kazanacaksın.")
			say_color("yellow","Unutma Sadece 7 Günlüktür...")
			say_color("yellow","VIP olmak istiyor musun?")
			local s = select("Evet", "Hayır")
			if s == 1 then
				pc.remove_item(81200,1)
				say("VIP Bilgi    :")
				say("")
				say_color("green","Tebrikler" ..vip_isim)
				say_color("cyan","7 gün boyunca S-Type2 VIP üyesisin.")
				say_color("cyan","7 gün boyunca şu özelliklere sahip olacaksın;")
				say_color("cyan","VIP Tag")
				say_color("cyan","Savunma +140")
				say_color("cyan","Saldırı Değeri +60")
				say_color("cyan","Max.HP +3000")
				say_color("cyan","Yarı insanlara karşı güçlü +%10")
				say_color("cyan","100.000.000 Yang")
				say_color("cyan","VIP Kostüm")
				say_color("cyan","İrade Gücü Yüzüğü")
				say_color("green","VIP ünvanı 6 saat içerisinde isminin başına eklenecektir.")      
				say_color("cyan","VIP üyeliğin keyfini çıkarın.")
				notice_all("Tebrikler, " .. pc . get_name ( ) .. " S-Type2 VIP üyesi oldu.")
				notice_all("Kendisini tebrik edip bizi seçtikleri için kendisine teşekkür ediyoruz.")
				chat("Savunma +140")
				chat("Saldırı Değeri +60")
				chat("Max.HP +3000")
				chat("Yarı insanlara karşı güçlü +%10")
				chat("İyi oyunlar dileriz... S-Type2")
				pc.change_money ("100000000")
				pc . give_item2("41326",1)
				pc . give_item2("71148",1)
				affect.remove_collect()
				affect.remove_collect(apply.ATTBONUS_HUMAN,10,60*60*24*7)
				affect.add_collect(apply.ATT_GRADE_BONUS,60,60*60*24*7)
				affect.add_collect(apply.DEF_GRADE_BONUS,140,60*60*24*7)
				affect.add_collect(apply.MAX_HP,3000,60*60*24*7)
				pc.setqf("vip",1)
				pc.setqf("vipsure",get_time()+60*60*24*7) -- vip süresini belirlemek için +60*60*24*7 = 7 gün demektir.
			else
				say_title("VIP: ")
				say("VIP üyeliği almadığın için üzgünüz.")
				say("Umarız en kısa sürede VIP üyemiz olursun.")
			end
		end
		when login with pc.getqf("vip")==0 and not npc . is_pc ( )begin
		end
		when 81200.use with pc.getqf("vip")==0 begin --- Kadın
			vip_isim = pc.get_name()
			say_title("VIP Sistemi")
			say_color("green","Merhabalar,"..vip_isim)
			say_color("yellow","S-Type2 VIP üyelik size bir çok şey kazandıracak,")
			say_color("yellow","Bunlardan biri isminin başına VIP eki gelmesidir.")
			say_color("yellow","Ek olarak sana bir çok özellik eklenecek.")
			say_color("yellow","Oyun içinde VIP Uyelere ozel kostüm kazanacaksın.")
			say_color("yellow","Unutma Sadece 7 Günlüktür...")
			say_color("yellow","VIP olmak istiyor musun?")
			local s = select("Evet", "Hayır")
			if s == 1 then
				pc.remove_item(81200,1)
				say_color("green","VIP Bilgi    :")
				say("")
				say_color("green","Tebrikler" ..vip_isim)
				say_color("cyan","7 gün boyunca S-Type2 VIP üyesisin.")
				say_color("cyan","7 gün boyunca şu özelliklere sahip olacaksın;")
				say_color("cyan","VIP Tag")
				say_color("cyan","Savunma +140")
				say_color("cyan","Saldırı Değeri +60")
				say_color("cyan","Max.HP +3000")
				say_color("cyan","Yarı insanlara karşı güçlü +%10")
				say_color("cyan","100.000.000 Yang")
				say_color("cyan","VIP Kostüm")
				say_color("cyan","İrade Gücü Yüzüğü")
				say_color("green","VIP ünvanı 6 saat içerisinde isminin başına eklenecektir.")      
				say_color("cyan","VIP üyeliğin keyfini çıkarın.")
				notice_all("Tebrikler, " .. pc . get_name ( ) .. " S-Type2 VIP üyesi oldu.")
				notice_all("Kendisini tebrik edip bizi seçtikleri için kendisine teşekkür ediyoruz.")
				chat("Savunma +140")
				chat("Saldırı Değeri +60")
				chat("Max.HP +3000")
				chat("Yarı insanlara karşı güçlü +%10")
				chat("İyi oyunlar dileriz... S-Type2")
				pc.change_money ("100000000")
				pc . give_item2("41327",1)
				pc . give_item2("71148",1)
				affect.remove_collect()
				affect.remove_collect(apply.ATTBONUS_HUMAN,10,60*60*24*7)
				affect.add_collect(apply.ATT_GRADE_BONUS,60,60*60*24*7)
				affect.add_collect(apply.DEF_GRADE_BONUS,140,60*60*24*7)
				affect.add_collect(apply.MAX_HP,3000,60*60*24*7)
				pc.setqf("vip",1)
				pc.setqf("vipsure",get_time()+60*60*24*7) -- vip süresini belirlemek için +60*60*24*7 = 7 gün demektir.
			else
				say_title("VIP: ")
				say_color("red","VIP üyeliği almadığın için üzgünüz.")
				say_color("red","Umarız en kısa sürede VIP üyemiz olursun.")
			end
		end

		when 81200.use with pc.getqf("vip")==1 begin --- Erkek
			say_title("S-Type2 VIP Sistemi:")
			say("")
			say_color("red","Zaten VIP üyesisin.")
			local kalansure = pc.getqf("vipsure")-get_time()
			local hesapla = math.floor(kalansure/60/60)
			say(pc . get_name ( ) .. " VIP üyeliğinin bitmesine "..hesapla.." saat kaldı.")
		end
		when 81200.use with pc.getqf("vip")==1 begin --- Kadın
			say_title("S-Type2 VIP Sistemi:")
			say("")
			say_color("red","Zaten VIP üyesisin.")
			local kalansure = pc.getqf("vipsure")-get_time()
			local hesapla = math.floor(kalansure/60/60)
			say_color("green", pc . get_name ( ) .. " VIP üyeliğinin bitmesine "..hesapla.." saat kaldı.")
		end
	end
end
