# Dragon Segfault data

share.tar.gz has the following:

tree share
├── 0011.DA3-1_1.fastp.fastq.gz
├── 0011.DA3-1_2.fastp.fastq.gz
├── command.sh
├── DA3.0011.dragmap.log
├── DA3.0011.sam
└── dragmap
    ├── hash_table.cfg
    ├── hash_table.cfg.bin
    ├── hash_table.cmp
    ├── hash_table_stats.txt
    ├── reference.bin
    ├── ref_index.bin
    ├── repeat_mask.bin
    └── str_table.bin

1 directory, 13 files

## To reproduce:

docker run --rm -v $(pwd):/data quay.io/biocontainers/dragmap:1.3.0--h91baf5a_3 /bin/bash -c 'cd /data &&  bash command.sh'

## output

2024-06-19 01:49:11 	[704abafb6740]	Version: 1.3.0
2024-06-19 01:49:11 	[704abafb6740]	argc: 13 argv: dragen-os -r dragmap --RGSM DA3_DA3 --RGID @RG\tID:HLVWFAFXX.DA3.1\tPU:1\tSM:DA3_DA3\tLB:DA3\tDS:s3://brentlab-ref/KN99/FungiDB-68_CneoformansKN99_Genome.fasta\tPL:ILLUMINA --num-threads 8 -1 0011.DA3-1_1.fastp.fastq.gz -2 0011.DA3-1_2.fastp.fastq.gz
decompHashTableCtxInit...
  0.004 seconds
decompHashTableHeader...
  0.001 seconds
decompHashTableLiterals...
  0.099 seconds
decompHashTableExtIndex...
  0.000 seconds
decompHashTableAutoHits...
  0.361 seconds
decompHashTableSetFlags...
  0.021 seconds
finished decompress
Running dual fastq workflow on 8 threads. System supports 32 threads.
0	249	0	0	0	0	10000	1	40000	1	1000	0	0	0	6	
0	250	0	0	0	0	10000	1	40000	1	1000	0	0	0	5	
0	251	0	0	0	0	10000	1	40000	1	1000	0	0	0	4	
0	252	0	0	0	0	10000	1	40000	1	1000	0	0	0	3	
0	253	0	0	0	0	10000	1	40000	1	1000	0	0	0	2	
0	254	0	0	0	0	10000	1	40000	1	1000	0	0	0	1	
command.sh: line 7:     7 Segmentation fault      (core dumped) dragen-os -r dragmap --RGSM DA3_DA3 --RGID "@RG\tID:HLVWFAFXX.DA3.1\tPU:1\tSM:DA3_DA3\tLB:DA3\tDS:s3://brentlab-ref/KN99/FungiDB-68_CneoformansKN99_Genome.fasta\tPL:ILLUMINA" --num-threads 8 -1 0011.DA3-1_1.fastp.fastq.gz -2 0011.DA3-1_2.fastp.fastq.gz 2> >(tee DA3.0011.dragmap.log >&2) > DA3.0011.sam

