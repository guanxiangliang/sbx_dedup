# Sunbeam extension sbx_dedup

This is a Sunbeam (https://github.com/sunbeam-labs) extension deduplicate the sequncing reads after QC step. The process will remove both optical and PCR deplicates using BBtools (https://jgi.doe.gov/data-and-tools/bbtools/bb-tools-user-guide/clumpify-guide/). I used this extension to process my virome reads, since some examples have too many duplicates, which stacked in a very small region of viral genomes, resulting in strong signals after classification.  

# Installing and running

Activate sunbeam and clone the repo to `sunbeam/extension`
```
source activate sunbeam
cd $SUNBEAM_DIR
git clone https://github.com/guanzhidao/sbx_dedup extensions/sbx_dedup
conda install --file extensions/sbx_dedup/requirements.txt
```

Remember to add dedup option to your sunbeam config file
```
cat $SUNBEAM_DIR/extensions/sbx_dedup/config.yml >> $PROJECT_DIR/sunbeam_config.yml
sunbeam run --configfile $PROJECT_DIR/sunbeam_config.yml all_dedup
```
