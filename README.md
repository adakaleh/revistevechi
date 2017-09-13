# reviste vechi

Baza de date se generează cu următoarele comenzi:
```
sqlite3 arhiva_reviste.db < schema.sql
sqlite3 arhiva_reviste.db < data.sql
```

Dump-ul se generează cu următoarele comenzi:
```
sqlite3 arhiva_reviste.db .schema > schema.sql
sqlite3 arhiva_reviste.db .dump > dump.sql
grep -vx -f schema.sql dump.sql > data.sql
rm dump.sql
sed -i 's/^PRAGMA foreign_keys=OFF;$/PRAGMA foreign_keys=ON;/g' data.sql
```

---

Valori editii('tip', 'parinte')

* revista, NULL
* supliment, editie_id
* almanah, editie_id

Valori editii('disc_demo')

* CD
* DVD
* CD, DVD

Valori download('categorie')

* revista
* disc_CD
* disc_DVD
* disc_CD_scan
* disc_DVD_scan
* coperta_CD
* coperta_DVD



#### Neimplementat inca

Valori editii('scan_status')

* complet_OK
* complet_nesatisfacator
* incomplet_OK
* incomplet_nesatisfacator
