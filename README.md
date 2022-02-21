# №1
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
# №2e
![image](https://user-images.githubusercontent.com/22128700/155002259-7db73d43-19c4-449b-bfcf-ec57067be7dd.png)
Как видно из гистограмм, на стадии ICM процент метилирования ДНК самый маленький, в то время как на более ранней 8cell и более поздней epiblast стадиях процент метилирования растёт, что соответствует реальной картине.
![image](https://user-images.githubusercontent.com/22128700/155002749-9410d3f8-99fc-48d1-8a60-4709868813d3.png)
