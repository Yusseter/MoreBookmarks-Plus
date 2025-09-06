# surekli hata var! dikkat! sifirda yapilacak! denilenler disinda baska degisiklik yapilmayacak! simdi yapacaklarini tek tek yeniden anlatiyorum:

- simdi, oncelikle "z_YB_zOverride.txt" dosyasinda karakter bloklarini bul. Ornegin;

1413922 = {
	name = "Zhaoming"
	culture = khitan
	religion = eastern_tengri
	1101.1.1 = {
		birth = yes
	}
	1134.1.1 = { # Yusseter
		culture = qitai
	}
}

- simdi bu karakter blogunun id sini tanimla. burda 1413922 bu id nin "00_MONGOLIC.txt" dosyasindaki karsiligini bul. burda;

1413922 = { #蕭昭明 Xiao Zhaoming. (大耶律初魯得迪魯菫將軍妻撻體娘子墓誌銘)
	dynasty = 1000049120 #Chulude 初魯德部/楮特部
	name = "Zhaoming"
	religion = eastern_tengri
	culture = khitan
	father = 1413921
	mother = 1413402
	1101.1.1 = {
		birth = yes
	}
	1116.1.1 = { employer = 194334 }
	1177.11.11 = {
		death = yes
	}
}

- simdi "z_YB_zOverride.txt" dosyasinda yapilan culture degisikligine bakalim normal culture si "khitan" 1134 yilinda "qitai" culturu nu almis simdi bu blokta bu culture degisiklerini ekleyelim:

1413922 = { #蕭昭明 Xiao Zhaoming. (大耶律初魯得迪魯菫將軍妻撻體娘子墓誌銘)
	dynasty = 1000049120 #Chulude 初魯德部/楮特部
	name = "Zhaoming"
	religion = eastern_tengri
	culture = khitan
	father = 1413921
	mother = 1413402
	1101.1.1 = {
		birth = yes
	}
	1116.1.1 = { employer = 194334 }
	1134.1.1 = { # Yusseter
		culture = qitai
	}
	1177.11.11 = {
		death = yes
	}
}

- kronolojik olarak tarihsel olan culture degisiklini bu sekilde ekledik ve # Yusseter etiketi ile benim yaptigim bilgisini de ekledik.

- simdi tarihsel olmayan culture degisikliklerine bakalim: "z_YB_zOverride.txt" de su var:

1413862 = {
	name = "Miji"
	female = yes
	culture = qitai # Yusseter
	#culture = khitan
	1163.1.1 = {
		birth = yes
	}
}

- burda tarihsel bir culture degisikligi yok. bakalim bunu nasil bir sekilde "00_MONGOLIC.txt" dosyasina aktarmamiz gerekiyormus:

1413862 = { #蕭迷己 Xiao Miji, courtesy name 吼魯宛 Houruwan. Second daughter of Huwuli according to 拔里公墓誌. Married her mother's younger brother 石丑.
	dynasty = 1000102403 #Bali
	name = "Miji"
	culture = qitai # Yusseter
	#culture = khitan
	religion = kegon
	father = 1413680
	female= yes
	1163.1.1 = {
		birth= yes
	}
	1205.1.1 = {
		death = yes
	}
}

- evet default culture kisiminda eski olan culture # yorum formuna getirilerek devre disi birakilmis. ve bir ust satirina yeni culture eklenmis ve # Yusseter yorumu ile yapilan degisiklik belirtilmis. ve baska hic bir alakasiz degisiklik yapilmamis.

- ornek cogu zaman olan hata(lar):

- 1- cikti da culture = khitan culture dosyasinda iki adet var. birisi normal hali digeri # ile yorum formuna getirilmis hali normal hala hala durdugu icin yorum formu bir ise yaramiyor. 

1413862 = { #蕭迷己 Xiao Miji, courtesy name 吼魯宛 Houruwan. Second daughter of Huwuli according to 拔里公墓誌. Married her mother's younger brother 石丑.
	dynasty = 1000102403 #Bali
	name = "Miji"
	culture = khitan
	culture = qitai # Yusseter
	#culture = khitan
	religion = kegon
	father = 1413680
	female= yes
	1163.1.1 = {
		birth= yes
	}
	1205.1.1 = {
		death = yes
	}
}

- boyle degilde soyle yapmalisin:

1413862 = { #蕭迷己 Xiao Miji, courtesy name 吼魯宛 Houruwan. Second daughter of Huwuli according to 拔里公墓誌. Married her mother's younger brother 石丑.
	dynasty = 1000102403 #Bali
	name = "Miji"
	culture = qitai # Yusseter
	#culture = khitan
	religion = kegon
	father = 1413680
	female= yes
	1163.1.1 = {
		birth= yes
	}
	1205.1.1 = {
		death = yes
	}
}

- 2- sen her zaman degisiklik yaptigin karakter block larinda id ler icin tanim olan suslu parantezler in kapatan parantezleri siliyorsun, bu hem hatali bir sonuc veriyor, hemde komutun disinda bir islem yapmis oluyorsun ornek:

siaumb3 = { #
	name = "Juerbiesu"
	dynasty = 1000049119 #蕭2
	culture = qitai # Yusseter
	#culture = khitan
	religion = "kegon"
	female = yes
	father = siaumb1

	1167.1.1 = {
		birth = yes
	}

	1221.1.1 = {
		death = yes
	}


- boyle yapmak yerine soyle yapmalisin:

siaumb3 = { #
	name = "Juerbiesu"
	dynasty = 1000049119 #蕭2
	culture = qitai # Yusseter
	#culture = khitan
	religion = "kegon"
	female = yes
	father = siaumb1

	1167.1.1 = {
		birth = yes
	}

	1221.1.1 = {
		death = yes
	}
}

# bu teknik olarak bir sorun degil ama ornegin, burda:

1413680 = { #蕭胡烏里 Xiao Huwuli, courtesy name 緬隱 Mianyin. Son of Shunian according to 拔里公墓誌. Married 楚烈 of 惕隠司仲父房.
	dynasty = 1000102403 #Bali
	name = "Huwuli"
	culture = khitan
	religion = kegon
	father = 1413678
	1130.1.1 = {
		birth= yes
	}
	1175.1.1 = {
		death = yes
	}

	1134.1.1 = { # Yusseter
		culture = qitai
	}
}

- bu kisimda 

	1134.1.1 = { # Yusseter
		culture = qitai
	}

- kisimi kronolojik ilerlemiyor. ayni zamanda buda bir sorun degil ama arada bir tane normalde oldugundan fazla satir bosluk biraktigin icin kodun yapisi biraz kotu gozukuyor
ornegin bunu su sekilde yapsan daha guzel olurdu:

1413680 = { #蕭胡烏里 Xiao Huwuli, courtesy name 緬隱 Mianyin. Son of Shunian according to 拔里公墓誌. Married 楚烈 of 惕隠司仲父房.
	dynasty = 1000102403 #Bali
	name = "Huwuli"
	culture = khitan
	religion = kegon
	father = 1413678
	1130.1.1 = {
		birth= yes
	}
	1134.1.1 = { # Yusseter
		culture = qitai
	}
	1175.1.1 = {
		death = yes
	}
}

# hayir baska degisiklikler de var ornegin soyle gostereyim

- "z_YB_zOverride1.txt" deki form:

32911 = {
	name = "S_adi"
	#dynasty_house = house_rawwadid # Yusseter
	religion = "ashari"
	culture = kurdish # Yusseter
	#culture = azeri # Yusseter
	1080.1.1 = {
		birth = "1080.1.1"
	}
}

- "00_MIDDLE_EAST.txt" deki form:

32911 = {
	name = "S_adi"
	dynasty_house = house_Ayyubid
	religion = "ashari"
	culture = "kurdish"
	father = 159156
	mother = 159157
	1080.1.1 = {
		birth = "1080.1.1"
	}
	1130.1.1 = {
		death = yes
	}
}

- olmasi gereken duzenlenmis sonuc:

32911 = {
	name = "S_adi"
	dynasty_house = house_Ayyubid
	religion = "ashari"
	culture = "kurdish"
	#culture = azeri # Yusseter
	father = 159156
	mother = 159157
	1080.1.1 = {
		birth = "1080.1.1"
	}
	1130.1.1 = {
		death = yes
	}
}

- senin yaptigin duzenlenmis sonuc:

32911 = { # Sadi Rawwadid
	dynasty = 1000543210
	name = "Sadi"
	religion = "ashari"
	culture = kurdish # Yusseter
	#culture = azeri
	1080.1.1 = {
		birth = "1080.1.1"
	}
	1140.1.1 = {
		death = "1140.1.1"
	}
}

# yine ayni durum, baska degisiklikler de var ornegin soyle gostereyim

- "z_YB_zOverride1.txt" deki form:

159169 = {
	name = "Bilal_Hecebani"
	religion = "ashari"
	culture = azeri # Yusseter
	820.1.1 = {
		birth = "820.1.1"
	}
}

- "00_MIDDLE_EAST.txt" deki form:

159169 = {
	name = "Bilal_Hecebani"
	dynasty = 1029007
	religion = "ashari"
	culture = "kurdish"
	father = BilalFather
	820.1.1 = {
		birth = "820.1.1"
	}
	886.1.1 = {
		death = yes
	}
}

- olmasi gereken duzenlenmis sonuc:

159169 = {
	name = "Bilal_Hecebani"
	dynasty = 1029007
	religion = "ashari"
	culture = azeri # Yusseter
	#culture = "kurdish"
	father = BilalFather
	820.1.1 = {
		birth = "820.1.1"
	}
	886.1.1 = {
		death = yes
	}
}

- senin yaptigin duzenlenmis sonuc:

159169 = {
	name = "Bilal_Hecebani"
	dynasty_house = house_Hecebani
	religion = "ashari"
	culture = azeri # Yusseter
	#culture = "persian"
	820.1.1 = {
		birth = "820.1.1"
	}
	870.1.1 = {
		death = yes
	}
}

# bu teknik olarak sorun degil ama # Yusseter i yanlis kullaniyorsun. sen # ile yorum formuna aldigin satirda yeniden # Yusseter yaziyorsun, boyle yapma. onun yerine yeni ekledigin satirin sonuna " # Yusseter" ekle. boyece hangi satirin yeni eklendigi ve hangi satirin # ile yorum formuna getirilerek iptal edildigi gozuke bilir. ornegin:

226012 = {
	name = "Naser_ed-Din_Muhammad"
	dynasty_house = house_Ayyubid
	religion = "ashari"
	culture = "azeri" # Yusseter
	#culture = "levantine" # Yusseter
	father = 32912
	1140.1.1 = {
		birth = "1140.1.1"
	}
	1150.1.1 = { # Yusseter
		culture = levantine
	}
	1186.3.5 = {
		death = yes
	}
}

- bunu yerine

226012 = {
	name = "Naser_ed-Din_Muhammad"
	dynasty_house = house_Ayyubid
	religion = "ashari"
	culture = "azeri" # Yusseter
	#culture = "levantine"
	father = 32912
	1140.1.1 = {
		birth = "1140.1.1"
	}
	1186.3.5 = {
		death = yes
	}
}

- bu sekilde

# bu teknik olarak bir sorun degil ama ornegin, burda:

226012 = {
	name = "Naser_ed-Din_Muhammad"
	dynasty_house = house_Ayyubid
	religion = "ashari"
	culture = "azeri" # Yusseter
	#culture = "levantine"
	father = 32912
	1140.1.1 = {
		birth = "1140.1.1"
	}
	1186.3.5 = {
		death = yes
	}

	1140.1.1 = {
		birth = "1140.1.1"
	}
	1150.1.1 = { # Yusseter
		culture = levantine
	}
}

- bu kisimda 

	1150.1.1 = { # Yusseter
		culture = levantine
	}

kisimi kronolojik ilerlemiyor. ayni zamanda buda bir sorun degil ama arada bir tane normalde oldugundan fazla satir bosluk biraktigin icin kodun yapisi biraz kotu gozukuyor
ornegin bunu su sekilde yapsan daha guzel olurdu:

226012 = {
	name = "Naser_ed-Din_Muhammad"
	dynasty_house = house_Ayyubid
	religion = "ashari"
	culture = "azeri" # Yusseter
	#culture = "levantine"
	father = 32912
	1140.1.1 = {
		birth = "1140.1.1"
	}
	1150.1.1 = { # Yusseter
		culture = levantine
	}
	1186.3.5 = {
		death = yes
	}
}

ve soyle bir hatan var. birth iceren tarih block unu duplicate etmissin (kopyalamissin) ve death iceren tarih block unda normalde death = yes ibaresi varken sen, death = 1186.3.5 icin boyle kullanmissin (tarih block unun tarihini death icin kullanmissin)

- bunun yerine:

226012 = {
	name = "Naser_ed-Din_Muhammad"
	dynasty_house = house_Ayyubid
	religion = "ashari"
	culture = "azeri" # Yusseter
	#culture = "levantine"
	father = 32912
	1140.1.1 = {
		birth = "1140.1.1"
	}
	1186.3.5 = {
		death = yes
	}

	1140.1.1 = {
		birth = "1140.1.1"
	}
	1150.1.1 = { # Yusseter
		culture = levantine
	}
}

- bu:

226012 = {
	name = "Naser_ed-Din_Muhammad"
	dynasty_house = house_Ayyubid
	religion = "ashari"
	culture = "azeri" # Yusseter
	#culture = "levantine"
	father = 32912
	1140.1.1 = {
		birth = "1140.1.1"
	}
	1150.1.1 = { # Yusseter
		culture = levantine
	}
	1186.3.5 = {
		death = yes
	}
}

# olur. bunu yaptiktan sonra "00_MONGOLIC.txt" dosyasi icin yaptigin bu rapor u "00_MIDDLE_EAST.txt" icinde yap `file:CK3_culture_patch_audit.txt`

# cok fazla hata var! dikkat! sifirda yapilacak! denilenler disinda baska degisiklik yapilmayacak! simdi yapacaklarini tek tek yeniden anlatiyorum:

- simdi, oncelikle "z_YB_zOverride1.txt" dosyasinda karakter bloklarini bul. Ornegin;

226000 = {
	name = "Yusuf"
	religion = "ashari"
	culture = azeri # Yusseter
	1138.1.1 = {
		birth = yes
	}
	1150.1.1 = { # Yusseter
		culture = syromesopotamian_turkish
	}
}

- simdi bu karakter blogunun id sini tanimla. burda 1413922 bu id nin "00_MIDDLE_EAST.txt" dosyasindaki karsiligini bul. burda;

226000 = {
	name = "Yusuf" #Egypt
	dynasty_house = house_Ayyubid
	dna = bookmark_saladin_226000
	diplomacy = 8
	martial = 8
	stewardship = 10
	intrigue = 7
	learning = 7
	prowess = 5
	religion = "ashari"
	culture = "levantine"
	trait = diligent
	trait = calm
	trait = generous
	trait = just
	trait = education_martial_4
	trait = faith_warrior
	trait = shrewd
	father = 226053
	1138.1.1 = {
		birth = "1138.1.1"
		give_nickname = nick_saladin
	}
	1157.1.1 = {
		add_pressed_claim = title:d_aleppo
		add_pressed_claim = title:d_palmyra
		add_pressed_claim = title:d_damascus
		add_pressed_claim = title:d_amman
		add_pressed_claim = title:d_oultrejourdain
	}
	1171.8.2 = {
		effect = {
			rightfully_imprison_character_effect = {
				TARGET = character:32910M
				IMPRISONER = character:226000
			}
		}
	}
	1178.1.1 = {
		give_nickname = nick_salah_al_din
		add_prestige = 2000
		add_piety = 1000
		add_prestige_level = 2
		add_piety_level = 2
		add_gold = 400
		if = {
			limit = { has_realm_law = crown_authority_0 }
			add_realm_law = crown_authority_1
		}
	}
	1180.1.1 = {
		capital = c_aleppo
	}
	1193.3.4 = {
		death = {
			death_reason = death_ill
		}
	}
}

- simdi "z_YB_zOverride1.txt" dosyasinda yapilan culture degisikligine bakalim normal culture si "levantine" 1150 yilinda "syromesopotamian_turkish" culturu nu almis simdi bu blokta bu culture degisiklerini ekleyelim:

226000 = {
	name = "Yusuf" #Egypt
	dynasty_house = house_Ayyubid
	dna = bookmark_saladin_226000
	diplomacy = 8
	martial = 8
	stewardship = 10
	intrigue = 7
	learning = 7
	prowess = 5
	religion = "ashari"
	culture = "levantine"
	trait = diligent
	trait = calm
	trait = generous
	trait = just
	trait = education_martial_4
	trait = faith_warrior
	trait = shrewd
	father = 226053
	1138.1.1 = {
		birth = "1138.1.1"
		give_nickname = nick_saladin
	}
	1150.1.1 = { # Yusseter
		culture = syromesopotamian_turkish
	}
	1157.1.1 = {
		add_pressed_claim = title:d_aleppo
		add_pressed_claim = title:d_palmyra
		add_pressed_claim = title:d_damascus
		add_pressed_claim = title:d_amman
		add_pressed_claim = title:d_oultrejourdain
	}
	1171.8.2 = {
		effect = {
			rightfully_imprison_character_effect = {
				TARGET = character:32910M
				IMPRISONER = character:226000
			}
		}
	}
	1178.1.1 = {
		give_nickname = nick_salah_al_din
		add_prestige = 2000
		add_piety = 1000
		add_prestige_level = 2
		add_piety_level = 2
		add_gold = 400
		if = {
			limit = { has_realm_law = crown_authority_0 }
			add_realm_law = crown_authority_1
		}
	}
	1180.1.1 = {
		capital = c_aleppo
	}
	1193.3.4 = {
		death = {
			death_reason = death_ill
		}
	}
}

- kronolojik olarak tarihsel olan culture degisiklini bu sekilde ekledik ve # Yusseter etiketi ile benim yaptigim bilgisini de ekledik.

- simdi burda tarihsel olmayan culture degisikliklerine bakalim: "z_YB_zOverride1.txt" de su var:

226000 = {
	name = "Yusuf" #Egypt
	dynasty_house = house_Ayyubid
	dna = bookmark_saladin_226000
	diplomacy = 8
	martial = 8
	stewardship = 10
	intrigue = 7
	learning = 7
	prowess = 5
	religion = "ashari"
	culture = "levantine"
	trait = diligent
	trait = calm
	trait = generous
	trait = just
	trait = education_martial_4
	trait = faith_warrior
	trait = shrewd
	father = 226053
	1138.1.1 = {
		birth = "1138.1.1"
		give_nickname = nick_saladin
	}
	1150.1.1 = { # Yusseter
		culture = syromesopotamian_turkish
	}
	1157.1.1 = {
		add_pressed_claim = title:d_aleppo
		add_pressed_claim = title:d_palmyra
		add_pressed_claim = title:d_damascus
		add_pressed_claim = title:d_amman
		add_pressed_claim = title:d_oultrejourdain
	}
	1171.8.2 = {
		effect = {
			rightfully_imprison_character_effect = {
				TARGET = character:32910M
				IMPRISONER = character:226000
			}
		}
	}
	1178.1.1 = {
		give_nickname = nick_salah_al_din
		add_prestige = 2000
		add_piety = 1000
		add_prestige_level = 2
		add_piety_level = 2
		add_gold = 400
		if = {
			limit = { has_realm_law = crown_authority_0 }
			add_realm_law = crown_authority_1
		}
	}
	1180.1.1 = {
		capital = c_aleppo
	}
	1193.3.4 = {
		death = {
			death_reason = death_ill
		}
	}
}

- suan burda tarihsel bir culture degisikligi yok. bakalim bunu nasil bir sekilde "00_MIDDLE_EAST.txt" dosyasina aktarmamiz gerekiyormus:

226000 = {
	name = "Yusuf" #Egypt
	dynasty_house = house_Ayyubid
	dna = bookmark_saladin_226000
	diplomacy = 8
	martial = 8
	stewardship = 10
	intrigue = 7
	learning = 7
	prowess = 5
	religion = "ashari"
	culture = azeri # Yusseter
	#culture = "levantine"
	trait = diligent
	trait = calm
	trait = generous
	trait = just
	trait = education_martial_4
	trait = faith_warrior
	trait = shrewd
	father = 226053
	1138.1.1 = {
		birth = "1138.1.1"
		give_nickname = nick_saladin
	}
	1150.1.1 = { # Yusseter
		culture = syromesopotamian_turkish
	}
	1157.1.1 = {
		add_pressed_claim = title:d_aleppo
		add_pressed_claim = title:d_palmyra
		add_pressed_claim = title:d_damascus
		add_pressed_claim = title:d_amman
		add_pressed_claim = title:d_oultrejourdain
	}
	1171.8.2 = {
		effect = {
			rightfully_imprison_character_effect = {
				TARGET = character:32910M
				IMPRISONER = character:226000
			}
		}
	}
	1178.1.1 = {
		give_nickname = nick_salah_al_din
		add_prestige = 2000
		add_piety = 1000
		add_prestige_level = 2
		add_piety_level = 2
		add_gold = 400
		if = {
			limit = { has_realm_law = crown_authority_0 }
			add_realm_law = crown_authority_1
		}
	}
	1180.1.1 = {
		capital = c_aleppo
	}
	1193.3.4 = {
		death = {
			death_reason = death_ill
		}
	}
}

- evet default culture kisiminda eski olan culture # yorum formuna getirilerek devre disi birakilmis. ve bir ust satirina yeni culture eklenmis ve # Yusseter yorumu ile yapilan degisiklik belirtilmis. ve baska hic bir alakasiz degisiklik yapilmamis.

- ornek cogu zaman olan hata(lar):

- 1- satirlar in baslarinda eksik bosluklar var. bu bosluklar bir hataya sebep olmaz ama oldukca kotu gozukuyor

32916 = {
	name = "Tughtekin"
	dynasty_house = house_Ayyubid
	religion = "ashari"
	syromesopotamian_turkish # Yusseter
	#culture = "egyptian"
	father = 226053
1148.1.1 = {
		birth = "1148.1.1"
	}
1197.1.1 = {
		death = yes
	}
}

- boyle degilde soyle yapmalisin:

32916 = {
	name = "Tughtekin"
	dynasty_house = house_Ayyubid
	religion = "ashari"
	culture = syromesopotamian_turkish # Yusseter
	#culture = "egyptian"
	father = 226053
	1148.1.1 = {
		birth = "1148.1.1"
	}
	1197.1.1 = {
		death = yes
	}
}

- 2- parantezler duzensiz ve hizasi. yine oncekinde oldugu gibi, bir hataya sebep olmaz ama oldukca kotu gozukuyor. ve ekledigin culture = levantine iceren tarih block u kronolojik degil

226012 = {
	name = "Naser_ed-Din_Muhammad"
	dynasty_house = house_Ayyubid
	religion = "ashari"
	"azeri" # Yusseter
	#culture = "levantine"
	father = 32912
	1140.1.1 = {
		birth = "1140.1.1"
	}
	1186.3.5 = {
		death = yes
	}
	1150.1.1 = { # Yusseter
		culture = levantine
	}}

- boyle yapmak yerine soyle yapmalisin:

226012 = {
	name = "Naser_ed-Din_Muhammad"
	dynasty_house = house_Ayyubid
	religion = "ashari"
	culture = "azeri" # Yusseter
	#culture = "levantine"
	father = 32912
	1140.1.1 = {
		birth = "1140.1.1"
	}
	1150.1.1 = { # Yusseter
		culture = levantine
	}
	1186.3.5 = {
		death = yes
	}
}

# 1. Satır hizası (indent) farklılıkları
- bu degisiklikleri sen yaptiysan orijinaline cevir. ornegin ben sunu fark ettim:

- orijinal hali:
1229951 = {
	name="Saljuq Shah"
	dynasty_house = house_oghuzSeljuks
	religion="maturidi"
	culture="turkish"
	father=144014
	1108.6.6={
		birth=yes
	}
	1141.1.1={ #? probably died in captivity after Boz-Aba dethroned him in Fars
		death={
			death_reason=death_dungeon
			killer=1229916
		}
	}
}

- override si:
1229951 = {
	name = "Saljuq Shah"
	religion = maturidi
	culture = persian_turkish # Yusseter
	1108.6.6 = {
		birth = yes
	}
}

- olmasi gereken:
1229951 = {
	name="Saljuq Shah"
	dynasty_house = house_oghuzSeljuks
	religion="maturidi"
	culture = persian_turkish # Yusseter
	#culture="turkish"
	father=144014
	1108.6.6={
		birth=yes
	}
	1141.1.1={ #? probably died in captivity after Boz-Aba dethroned him in Fars
		death={
			death_reason=death_dungeon
			killer=1229916
		}
	}
}

- senin yaptigin:
1229951 = {
	name="Saljuq Shah"
	dynasty_house = house_oghuzSeljuks
	religion="maturidi"
	culture = persian_turkish # Yusseter
	#culture = "turkish"
	father=144014
1108.6.6={
		birth=yes
	}
1141.1.1={ #? probably died in captivity after Boz-Aba dethroned him in Fars
		death={
			death_reason=death_dungeon
			killer=1229916
		}
	}
}

boyle yapma satir hizalari ni sen degistirme eger sen degistirmeden once boyle bir sey varsa onlara dokunma. kendin yaptiklarini duzelt

2. Override’da olup 00_TURKIC’te bulunmayan ID’ler
- bunlar onemli degil hem az sayida lar bu id leri gormezden gel

3. Çakışmalar
- bunlarada sen yinede sen kendin yapman gerekenleri bunlarada yap, geri kalani ben hallederim

# sanirim yine basi "satır hizaları" problemin den oldu

- ornegin:
1229940 = {
	name="Saljuqa Khatun" #married to Artuqid Nur al-Din Muhammad, then caliph al-Nasir
	female=yes
	dynasty_house = house_oghuzSeljuks
	religion="maturidi"
	culture = persian_turkish # Yusseter
	#culture = "turkish"
	father=225000
	1150.1.1={ #?
		birth=yes
	
culture = anatolian_turkish
}
	1167.1.1={ #by 1180
		add_spouse=144072
	}
	1185.1.1={ #after Nur al-Din Muhammad's death
		add_spouse=227000
	}
	1188.1.1={
		death=yes
	}
}

- sanirim burda kafan karisti cunku sen normalde culture = anatolian_turkish kisimini 1150.1.1 tarihi icin yapacaktin. ama zaten bu history block u vardi. sende icine koymak istedin ama tam olmadi, birde ayni zamanda o history block unun sonun da " #?" seklinde bir yorum vardi ve eklemen gereken " # Yusseter" yorumunu nereye ekleyecegini bilemedin ve boyle bir sorun olustu. bunu onune gecebilmek icin soyle yapmalisin, eger zaten ekleyecegin history block u mevcutsa onun block un icinde mevcut satirin bi alt satirina culture override sini yap. ama eger birde o history block unda bir yorum yaziyorsa bu sefer ekleyecegin "# Yusseter" yorumunu culture override satirinin yanina yaz.
ayni surda olacagi gibi:

1229940 = {
	name="Saljuqa Khatun" #married to Artuqid Nur al-Din Muhammad, then caliph al-Nasir
	female=yes
	dynasty_house = house_oghuzSeljuks
	religion="maturidi"
	culture = persian_turkish # Yusseter
	#culture="turkish"
	father=225000
	1150.1.1={ #?
		birth=yes
        culture = anatolian_turkish # Yusseter
	}
	1167.1.1={ #by 1180
		add_spouse=144072
	}
	1185.1.1={ #after Nur al-Din Muhammad's death
		add_spouse=227000
	}
	1188.1.1={
		death=yes
	}
}

# sanirim yine basi "parantez hizasi" ve "kronolojik" siralama problemi oldu

- ornegin burda sonda parantez iki tane art art a gelmis. aslinda son parantezin bir alt satirda culture id sinin hizasinda olmaliydi ve ayni zaman da burda kronoloji sorunuda var. ve bos yere normal de override dosyasinda olmayan islevsiz bir "culture = turkish # Yusseter" override si de yapmissin:
20678 = {
	name = "Abdul-Rahman"
	dynasty = 101033
	martial = 4
	diplomacy = 7
	intrigue = 6
	stewardship = 4
	religion = "maturidi"
	culture = turkish # Yusseter
	#culture = "turkish"
	trait = education_learning_3
	1039.1.1 = {
		birth = "1039.1.1"
	}
	1089.1.1 = {
		death = yes
	}
	1050.1.1 = {
	culture = persian_turkish # Yusseter
	}}

 - olmasi gereken

 20678 = {
	name = "Abdul-Rahman"
	dynasty = 101033
	martial = 4
	diplomacy = 7
	intrigue = 6
	stewardship = 4
	religion = "maturidi"
	culture = "turkish"
	trait = education_learning_3
	1039.1.1 = {
		birth = "1039.1.1"
	}
	1050.1.1 = {
		culture = persian_turkish # Yusseter
	}
	1089.1.1 = {
		death = yes
	}
}

 - yada boyledde olabilir:
 20678 = {
	name = "Abdul-Rahman"
	dynasty = 101033
	martial = 4
	diplomacy = 7
	intrigue = 6
	stewardship = 4
	religion = "maturidi"
	culture = "turkish"
	trait = education_learning_3
	1039.1.1 = {
		birth = "1039.1.1"
	}
	1050.1.1 = { # Yusseter
		culture = persian_turkish
	}
	1089.1.1 = {
		death = yes
	}
}

- lutfen bu problemleri hallet her seyi aklinda tut derin analizler yap ve sorunlari coz!