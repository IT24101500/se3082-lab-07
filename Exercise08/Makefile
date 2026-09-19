CC = mpicc
NP = 4

PROGS = sum_bcast sum_scatter sum_gather sum_reduce sum_allreduce sum_scan

SRC_sum_bcast      = ../Exercise01/sum_bcast.c
SRC_sum_scatter    = ../Exercise02/sum_scatter.c
SRC_sum_gather     = ../Exercise03/sum_gather.c
SRC_sum_reduce     = ../Exercise04/sum_reduce.c
SRC_sum_allreduce  = ../Exercise05/sum_allreduce.c
SRC_sum_scan       = ../Exercise06/sum_scan.c

.PHONY: all run clean

all: $(PROGS)

sum_bcast: $(SRC_sum_bcast)
	$(CC) -o $@ $<

sum_scatter: $(SRC_sum_scatter)
	$(CC) -o $@ $<

sum_gather: $(SRC_sum_gather)
	$(CC) -o $@ $<

sum_reduce: $(SRC_sum_reduce)
	$(CC) -o $@ $<

sum_allreduce: $(SRC_sum_allreduce)
	$(CC) -o $@ $<

sum_scan: $(SRC_sum_scan)
	$(CC) -o $@ $<

run: all
	@for p in $(PROGS); do \
		echo "=== $$p (np=$(NP)) ==="; \
		mpirun -np $(NP) ./$$p; \
		echo; \
	done

clean:
	rm -f $(PROGS)
