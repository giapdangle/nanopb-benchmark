CSRC = alltypes.c test-protobuf-embedded-c.c

all: results_all

include ../platform/Makefile

%.c: %.proto
	java -jar protoc.jar $<

simulation_size: alltypes.o
	size -t $^ | grep TOTALS | grep -o '[0-9]*' | head -n 1 > $@

results_all: results_1.0m2 results_1.0m3 results_1.0m4
	cat $^ > $@

results_1.0m2:
	echo 1.0M2 > simulation_version
	echo 2012-01-31 > simulation_date
	ln -sf protoc-1.0M2.jar protoc.jar
	ln -sf alltypes.h Alltypes.h
	make -B simulation_combined
	cp simulation_combined $@

results_1.0m3:
	echo 1.0M3 > simulation_version
	echo 2013-01-31 > simulation_date
	ln -sf protoc-1.0M3.jar protoc.jar
	ln -sf alltypes.h Alltypes.h
	make -B simulation_combined
	cp simulation_combined $@

results_1.0m4:
	echo 1.0M4 > simulation_version
	echo 2013-05-31 > simulation_date
	ln -sf protoc-1.0M4.jar protoc.jar
	ln -sf alltypes.h Alltypes.h
	make -B simulation_combined
	cp simulation_combined $@


