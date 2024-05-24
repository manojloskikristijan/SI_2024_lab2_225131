1. Kristijan Manojloski 225131



2. ![Untitled Diagram drawio](https://github.com/manojloskikristijan/SI_2024_lab2_225131/assets/126827297/49bfa134-6e94-40a0-a79a-4f496c0aa18e)
3. Ciklomatskata kompleksnost iznesuva 10, poradi toa shto spored formulata 7 if uslovi + 2 for loops + 1 = 10.
4. Spored Every Branch kriteriumot ima 7 test sluchai:
	- allItems е null (Go testira sluchajot kade 'allItems' e 'null')
	  Ochekuvan rezultat: RuntimeException
	- item so null ime i validen barcode (Gi testira grankite kade 'item.getName() == null' i 'item.getBarcode() != null' so validni karakteri vo barkodot)
	  Ochekuvan rezultat: True
	- item so prazno ime i nevaliden barcode (Gi testira grankite kade 'item.getName().length() == 0' i 'item.getBarcode() != null' i 'allowed.indexOf(c) == -1')
	  Ochekuvan rezultat: RuntimeException
	- item so null barcode (Go pokriva sluchajot kade 'item.getBarcode() == null')
	  Ochekuvan rezultat: RuntimeException
	- item so popust, cena > 300, i barcode koj zapochnuva so '0' (Gi pokriva grankite za validen barkod, popust > 0, cena > 300, i barkod koj zapochnuva so '0', rezultirajkji so dopolnitelno namaluvanje na cenata)
	  Ochekuvan rezultat: True
	- suma pomala od uplata (Ja testira grankata kade 'sum' e pomala od 'payment')
	  Ochekuvan rezultat: true
	- suma pogolema od uplata (Ja testira grankata kade 'sum' e pogolema od 'payment')
	  Ochekuvan rezultat: True
5. Spored Multiple Condition uslovot 'item.getPrice() > 300 && item.getDiscount() > 0 && item.getBarcode().charAt(0) == '0'', listata od itemi treba da sodrzhi:
	- (T, T, T) checkCart(Arrays.asList(new Item("item1", "012345", 350, 0.1f)), 320)
	- (T, T, F) checkCart(Arrays.asList(new Item("item1", "112345", 350, 0.1f)), 320)
	- (T, F, F) checkCart(Arrays.asList(new Item("item1", "112345", 350, 0)), 320)
	- (F, T, T) checkCart(Arrays.asList(new Item("item1", "012345", 200, 0.1f)), 320)
