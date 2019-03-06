## Mevcut "Dependency Treebank"'da bulunan hatalar.

Buradaki makalede belirtildiği üzere bazı konularda yanlış annotation yapılmış.
https://web.itu.edu.tr/gulsenc/papers/turcling2016_treebank.pdf
"However, its dependency grammarhas come to be criticized on occasion from various standpoints,and  it  is  known  to  contain  a  large  amount  of  annotationinconsistencies,  as  also  attested  in  some  previous  works"

Makale mevcut treebank (MST) üzerinde alternatifler öneriyor ve ardından isim değişikliği oluyor (IMST)
Makalenin tarihi olmadığı için mevcut durumu ne kadar yansıtıyor belli değil.

## StandfordNLP ile yayınlanan IMTS 1.2 modelinde bulunan hatalar


>Yanlış POS ve lemma tanımlı kelimeler
Ama ayakta kalmayı başardılar.  
ayakta,ayak/NOUN ama ayakta, ayakta/adverb,zarf olmalı.  
Hakkı'nın kız kardeşi benim adımı Karanlıkta Gelen Adam koydu bu olaydan sonra.  
karanlıkta/ADJ demiş ama TDK'ya göre isim  
http://tdk.org.tr/index.php?option=com_gts&arama=gts&guid=TDK.GTS.5c7a9b6dbcc661.69001173  

>Possesive sorunu.  
https://groups.google.com/d/msg/stanfordnlp/YEriIzcnDKo/1cYB_YvpBQAJ  
Burda sorduğum gibi, ingilizce parse 's ayrı token ama Türkçe'de 'nın birleşik.  
Lemma dataset'de varsa doğru > Tanrı'nın, Tanrı ama yoksa?  

>Tüm herfler büyük kelimenin NOUN olarak işaretlenmesi  
 EIB bu yıl Hırvatistan'a 500 milyon avro civarında yatırım yapacak  
text=EIB;lemma=Eob;upos=NOUN;xpos=Abr;  
?xpos=Abr den alınabilir mi?  

>Şirket isimlerinin NOUN+PROPN olması  
EIB bu yıl Hırvatistan'a 500 milyon avro civarında yatırım yapacak ve Telekom Srbija'nın çoğunluğu satışa çıkarıldı.  
Telekom/NOUN Srbija/PROPN  

>Özel isimleri noun yapması  
Mahkemede yaptığı konuşmada Hiseni, "Kosova'nın bağımsızlığı" ...  
text=Hiseni;lemma=hisen;upos=NOUN;xpos=Noun;  

>Sıfat yerine PROPN işaretlemesi  
Bayanlar plaj voleybolunda, Yunan çift Vasiliki Karantasiou ve Vasiliki Arvaniti Brezilyalı Renata Ribeiro ve Talita Rocha ikilisine 39-43 yenildi.  
Brezilyali/PROPN > Adjective olmalı  

>Yabancı kelimelerin PROPN olarak işaretlenmesi  
Ardından Annie Lennox'un "I Saved the World Today" (Bugün Dünyayı Kurtardım) adlı şarkısının çalınmasına.  
Foreign word olarak işaretlenmesi?  

>Yabancı kelimelerin alıntı olduğu yerde çıft tırnak ayrı PUNCT olarak gösterilmiyor.  
ardından Annie Lennox'un \"I Saved the World Today.\" (Bugün Dünyayı Kurtardım) adlı şarkısının  
<Token index=14;words=[<Word index=14;text="I;lemma="I;upos=PROPN;xpos=Prop;feats=Case=Nom|Number=Sing|Person=3;governor=12;dependency_relation=compound>]>  

>veya / ile ayrılmış kelimeler  
Tanınmış mimar/kent planlamacısı ve yerel British Graduates Society'nin başkanı Vassilis Zotos, buna katılmıyor ve sistemi eleştiriyor.  
mimar/kent tek kelime olarak PROPN geçiyor.  
"Petrol/doğal gaz boru hatları, enerji üreten barajları hedef almayı ve uluslararası sularda patlayıcı yüklü sürat tekneleriyle gemileri/petrol tankerlerini vurmayı planlıyordu."
