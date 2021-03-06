# statistics-gathering

This repo contains the necessary files required to collect & process the processor statistics on the simulations run.

Base code taken from https://github.com/ccelio/riscv-hpmcounters

HOW TO USE

To get this working, you first need to modify the linux boot loader. See https://github.com/rhit-neuro/deca/wikis/tutorials/statistics for instructions on how to do this.

MAKE the binary -
type 'make' to make the hpm_counters binary (the docker image should have riscv64-unknown-linux-gnu-g++ installed)


CONFIGURE benchmark script -
Edit the runstats.sh, replacing ./mybenchmark with the instruction required to run your benchmark.
If you want to collect statistcs once, instead of continuously, replace "./hpm_counters &" with "./hpm_counters single &"


MOVE the necessary files onto your mounted directory


LAUNCH your processor


ENSURE your benchmark is in the same directory as hpm_counters and runstats.sh (you may have to chmod +x runstats.sh)


RUN the benchmark
> ./runstats.sh


POWEROFF the rocketcore -
> poweroff

This is to ensure that the statistics.csv is properly saved


EXFILTRATE the statistics :

the statistics should be on the SD card as 'statistics.csv'


ANALYZE the statistics