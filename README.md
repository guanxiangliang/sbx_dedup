# Sunbeam extension sbx_dedup

This is a Sunbeam extension deduplicate the sequncing reads after QC step.

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
