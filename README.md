# Flood Susceptibility
 
Plugin QGIS para cálculo de suscetibilidade à inundação a partir de DEM, modelo HAND e dados de uso e ocupação do solo.
 
## O que o plugin faz
 
A partir de uma área de interesse (AOI) definida pelo usuário, o plugin:
 
1. Baixa automaticamente o DEM (Copernicus), o HAND (Alaska Satellite Facility) e o raster de uso e ocupação do solo (MapBiomas), recortados e reprojetados para a AOI
2. Calcula a declividade a partir do DEM
3. Reclassifica declividade, HAND e uso do solo numa escala comum de 1 a 5
4. Combina as três camadas reclassificadas por meio de uma soma ponderada, com pesos definidos pelo usuário
5. Gera o raster final de suscetibilidade à inundação, já estilizado em 5 classes

## Saída
 
O resultado final é um arquivo .tif em que cada pixel possui um valor de 1 a 5, representando a suscetibilidade à inundação calculada pela combinação ponderada das camadas de declividade, HAND e uso e ocupação do solo.
 
| Classe | Faixa |
|---|---|
| Muito Baixa | até 2,2 |
| Baixa | 2,2 a 3,0 |
| Média | 3,0 a 3,8 |
| Alta | 3,8 a 4,6 |
| Muito Alta | 4,6 a 5,0 |
 
## Como usar
 
1. Carregue no projeto QGIS uma camada vetorial representando a área de interesse (AOI)
2. Abra o plugin pelo menu ou ícone na barra de ferramentas
3. Selecione a camada da AOI
4. Defina os pesos de declividade, HAND e uso do solo (a soma deve ser igual a 1,0)
5. Defina o caminho de saída do raster final (opcional)
6. Clique em OK e aguarde o processamento

**OBS: Existe um shapefile para teste do plugin na pasta sample_data**
