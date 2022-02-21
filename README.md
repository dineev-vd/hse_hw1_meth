# Colab: [ссылка](https://colab.research.google.com/drive/1oUfnUF4hRnQzPVgvbJDlUyNkvppfVVIc?usp=sharing)
# №1
![image](https://user-images.githubusercontent.com/22128700/155006038-9600facc-69e9-468e-a40c-880719b8215c.png)
![image](https://user-images.githubusercontent.com/22128700/155006094-82fb16c2-b186-40a5-a228-479491f12a81.png)
![image](https://user-images.githubusercontent.com/22128700/155006117-e4b948fd-ac44-4173-b173-8a3a2304ed8b.png)

По сравнению с предыдушими ДЗ, могу выделить только отличие в меньшем кол-во дупликаций.
# №2a
|Название	 |chr11:11347700-11367700|	chr11:40185800-40195800|
|--- |---|---|
|	sorted_8cell.bam	|1090	|464|
|	sorted_epiblast.bam	|2328|	1062|
|	sorted_ICM.bam |	1456|	630|
# №2b
```bash
!find dna_meth/ | grep .bam | xargs -I NAME echo nohup deduplicate_bismark --bam --paired -o NAME NAME \> NAME \& | \
sed 's/dna_meth\///' | sed 's#/[^ ]*##' | sed 's/dna_meth\///2' |  sed 's#/[^ ]*#.out#2' | bash
```
|Название	 |Кол-во дупликаций (%) |
|--- |---|
|	8cell	| 521904 (18.31%) |
|	epiblast	|	205258 (2.92%) |
|	ICM |		377882 (9.08%) |
# №2d
## cell8
![image](https://user-images.githubusercontent.com/22128700/155003079-ae61ffdc-223d-47f6-a0ee-0bd9775bd095.png)
## ICM
![image](https://user-images.githubusercontent.com/22128700/155003120-b0610ee9-72d0-497f-a206-0704db38d816.png)
## epiblast
![image](https://user-images.githubusercontent.com/22128700/155003143-db603901-6043-48e4-8c0e-b707a377e5f1.png)
Если посмотреть на шкалу справа, можно заметить, что в средней стадии метилирование ДНК очень мало, в то время как в двух других в разы больше.
# №2e
![image](https://user-images.githubusercontent.com/22128700/155002259-7db73d43-19c4-449b-bfcf-ec57067be7dd.png)
Как видно из гистограмм, на стадии ICM процент метилирования ДНК самый маленький, в то время как на более ранней 8cell и более поздней epiblast стадиях процент метилирования растёт, что соответствует реальной картине.
![image](https://user-images.githubusercontent.com/22128700/155002749-9410d3f8-99fc-48d1-8a60-4709868813d3.png)
