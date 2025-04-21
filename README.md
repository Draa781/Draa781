permintaan.dapatkan('http://ws.audioscrobbler.com/2.0/?method=user.getrecenttracks&user=' + str(self.config["Amandeep Fams"]) + '&' + 'kunci_api=' + str(self.config["Amandeep Fams"]) + '&format=json' + '&limit=1')
        keluaran json = r.json()
        mencoba:
            sedang diputar = json_output['recenttracks']['track'][0]['@attr']['nowplaying']
            lulus
        kecuali KeyError:
            bermain = Salah
            lulus

        jika bermain == 'benar':
            nama_trek = json_output['recenttracks']['trek'][0]['nama']
            nama_artis = json_output['recenttracks']['track'][0]['artis']['#teks']
            nama_album = json_output['recenttracks']['track'][0]['album']['#teks']
            url_lagu = json_output['recenttracks']['track'][0]['url']
            formated_message = "Sedang Diputar" + "\n" + "Lagu: " + nama_lagu + "\n" + "Artis: " + nama_artis + "\n" + "Album: " + nama_album + "\n" + "URL Lagu: " + url_lagu
            tunggu utilitas.jawaban(pesan, str(pesan_yang_diformat))
        kalau tidak:
            nama_trek = json_output['recenttracks']['trek'][0]['nama']
            nama_artis = json_output['recenttracks']['track'][0]['artis']['#teks']
            nama_album = json_output['recenttracks']['track'][0]['album']['#teks']
            url_lagu = json_output['recenttracks']['track'][0]['url']
            tanggal_diputar = json_output['recenttracks']['track'][0]['tanggal']['#teks']
            formated_message = "Terakhir Diputar" + "\n" + "Lagu: " + str(nama_lagu) + "\n" + "Artis: " + str(nama_artis) + "\n" + "Album: " + str(nama_album) + "\n" + "URL Lagu: " + str(url_lagu) + "\n" + "Tanggal Diputar: " + str(tanggal_diputar) + " UTC"
            tunggu utilitas.jawaban(pesan, str(pesan_yang_diformat))
