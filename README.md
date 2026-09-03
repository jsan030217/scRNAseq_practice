# scRNAseq_practice
#1. scRNA_seq pipeline
#2. R vs Python 단계별 코드 비교
#3. 결과 해석

#1. scRAN_seq pipeline
#데이터불러오기 -> QC metric 계산 -> QC filtering -> Nomalization -> HVG selection -> Scaling -> PCA -> Neigbors -> UMAP -> Clustering -> marker gene check

#1-1 데이터 불러오기: 10X Genomics의 공개데이터 사용(cells X Genes 의 matrix)

#1-2 QC metric 계산+도표 시각화: 불러온 데이터에서 filtering 되어야 하는 부분 계산
#각 cell에서 발현되는 유전자 개수에 대한 count(n_genes_by_counts/nFeature_RNA)/세포당 총 UMI 수(total_counts/nCount_RNA)/미트콘드리아 유전자 비율(MT-)(pct_counts_mt/percent.mt)
#violin plot과 scatter plot을 이용하여 위의 각 항목에 대한 정보 시각화+분위수(percentile) 표 확인
#해당 plot을 보며 QC의 threshold value 확인

#1-3 QC filtering: QC metrix를 기반으로 임계값 결정 후 데이터 필터링
#저품질 세포를 실제로 matrix에서 제거

#1-4 Normalization: 세포별 총 UMI가 다르기 때문에, 이를 비교 분석하기 위해서 보정하는 과정
#발현량이 많은 
