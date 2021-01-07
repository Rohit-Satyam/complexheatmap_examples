# complexheatmap_examples

```r
l <- read.csv("matrix.txt", sep = "\t", header = T)
## convert file into matrix
t <- as.matrix(l[,c("AAAA","AABB","ABAA","ABAB","ABBA","ABBB","BAAA","BABA","BABB","BBAA")])

#assign rownames
rownames(t) <- l$filename
row_ha = rowAnnotation("Exon Percentage" = anno_barplot(l$Percentage.of.Exons.with.one.Gquad),width = unit(3, "cm"))
f2 = colorRamp2(seq(min(t), max(t), length = 3), c("#D6DBDF", "#C70039", "#900C3F"))
Heatmap(t,cluster_rows = FALSE,cluster_columns = FALSE,right_annotation = row_ha, col = f2, heatmap_legend_param=list(title = "Percentage"),heatmap_height = unit(2, "cm")*nrow(t))

``
