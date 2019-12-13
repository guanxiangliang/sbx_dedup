# Sunbeam extension sbx_dedup

This is a Sunbeam (https://github.com/sunbeam-labs) extension deduplicate the sequncing reads after QC step. The process will remove both optical and PCR deplicates using BBtools (https://jgi.doe.gov/data-and-tools/bbtools/bb-tools-user-guide/clumpify-guide/). I used this extension to process my virome reads, since some examples have too many duplicates, which stacked in a very small region of viral genomes, resulting in strong signals after classification.  

## Installing

To install:

    sunbeam extend https://github.com/guanzhidao/sbx_dedup

Config options for `sbx_dedup` are automatically added on `sunbeam init`. If you're installing an extension in a project where you already have a config file, run the following to add the options for your newly added extension to your config (the `-i` flag means in-place config file modification; remove the `-i` flag to see the new config in stdout):

    sunbeam config update -i sunbeam_config.yml

Dependencies are handled at runtime by snakemake, so you don't have to worry about them!

See legacy install instructions below.

## Running

To run:

    sunbeam run --configfile $PROJECT_DIR/sunbeam_config.yml --use-conda all_dedup

The `--use-conda` flag is required to let Snakemake know that you want to use the conda environment(s) included with your extension.

-------

## Legacy install instructions (Sunbeam <3.0)

Activate sunbeam and clone the repo to `sunbeam/extension`

```
source activate sunbeam
cd $SUNBEAM_DIR
git clone https://github.com/guanzhidao/sbx_dedup extensions/sbx_dedup
```

Remember to add dedup option to your sunbeam config file
```
cat $SUNBEAM_DIR/extensions/sbx_dedup/config.yml >> $PROJECT_DIR/sunbeam_config.yml
```
