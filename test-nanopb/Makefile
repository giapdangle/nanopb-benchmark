CSRC = alltypes.pb.c results.pb.c test-nanopb.c 
CSRC += nanopb/pb_encode.c nanopb/pb_decode.c
CFLAGS = -I nanopb -DPB_NO_ERRMSG

all: results_all

include ../platform/Makefile

%.pb: %.proto nanopb
	protoc -I. -Inanopb/generator -I/usr/include -o$@ $<

%.pb.c %.pb.h: %.pb nanopb
	python nanopb/generator/nanopb_generator.py $<

simulation_size: nanopb/pb_encode.o nanopb/pb_decode.o alltypes.pb.o results.pb.o
	size -t $^ | grep TOTALS | grep -o '[0-9]*' | head -n 1 > $@

results_all: results_0.1.1 results_0.1.2 \
			 results_0.1.3 results_0.1.4 results_0.1.5 \
			 results_0.1.6 results_0.1.7 results_0.1.8
	cat $^ > $@

results_0.1.1:
	rm -rf nanopb
	echo 0.1.1 > simulation_version
	echo 2012-01-14 > simulation_date
	mkdir nanopb
	tar xzf nanopb-0.1.1.tar.gz -C nanopb
	make -B simulation_combined
	cp simulation_combined $@

results_0.1.2:
	rm -rf nanopb
	echo 0.1.2 > simulation_version
	echo 2012-02-15 > simulation_date
	mkdir nanopb
	tar xzf nanopb-0.1.2.tar.gz -C nanopb
	make -B simulation_combined
	cp simulation_combined $@

results_0.1.3:
	rm -rf nanopb
	echo 0.1.3 > simulation_version
	echo 2012-06-12 > simulation_date
	mkdir nanopb
	tar xzf nanopb-0.1.3.tar.gz -C nanopb
	make -B simulation_combined
	cp simulation_combined $@

results_0.1.4:
	rm -rf nanopb
	echo 0.1.4 > simulation_version
	echo 2012-07-05 > simulation_date
	tar xzf nanopb-0.1.4.tar.gz
	make -B simulation_combined
	cp simulation_combined $@

results_0.1.5:
	rm -rf nanopb
	echo 0.1.5 > simulation_version
	echo 2012-08-04 > simulation_date
	tar xzf nanopb-0.1.5.tar.gz
	make -B simulation_combined
	cp simulation_combined $@

results_0.1.6:
	rm -rf nanopb
	echo 0.1.6 > simulation_version
	echo 2012-09-02 > simulation_date
	tar xzf nanopb-0.1.6.tar.gz
	make -B simulation_combined
	cp simulation_combined $@

results_0.1.7:
	rm -rf nanopb
	echo 0.1.7 > simulation_version
	echo 2012-11-11 > simulation_date
	tar xzf nanopb-0.1.7.tar.gz
	make -B simulation_combined
	cp simulation_combined $@

results_0.1.8:
	rm -rf nanopb
	echo 0.1.8 > simulation_version
	echo 2012-12-13 > simulation_date
	tar xzf nanopb-0.1.8.tar.gz
	make -B simulation_combined
	cp simulation_combined $@
