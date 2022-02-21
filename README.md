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
