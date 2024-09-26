
Data file, after downloading and decompressing the data, there is also an ALL.exe expression inside. Extract this expression file
https://drive.google.com/file/d/181Mk2-GxYQS4fi4Iw_s79oBc-texcdib/view?usp=sharing

Store files, this folder contains log information, model weights, and final result files. After decompression, 
you need to enter the adata folder and then decompress the result files
https://drive.google.com/file/d/1zI52yfTTJsJZayt9PaszshpXdhvyWRnR/view?usp=sharing

After completing the above preparations, the code can run normally


Use command 1 to process bulk data, and then use command 2 to predict single cells
 
1.python bulkmodel.py --drug "I.BET.762" --dimreduce "DAE" --encoder_h_dims "256,128" --predictor_h_dims "128,64" --bottleneck 512 --data_name "GSE110894" --sampling "upsampling" --dropout 0.1 --lr 0.5 --printgene "F" -mod "new" --checkpoint "save/bulk_pre/integrate_data_GSE110894_drug_I.BET.762_bottle_512_edim_256,128_pdim_128,64_model_DAE_dropout_0.1_gene_F_lr_0.5_mod_new_sam_upsampling"

2.python scmodel.py --sc_data "GSE110894" --dimreduce "DAE" --drug "I.BET.762" --bulk_h_dims "256,128" --bottleneck 512 --predictor_h_dims "128,64" --dropout 0.1 --printgene "F" -mod "new" --lr 0.5 --sampling "upsampling" --printgene "F" -mod "new" --checkpoint "save/sc_pre/integrate_data_GSE110894_drug_I.BET.762_bottle_512_edim_256,128_pdim_128,64_model_DAE_dropout_0.1_gene_F_lr_0.5_mod_new_sam_upsampling_DaNN.pkl"

Refer to the command above, the parameters for other datasets are included in the article.