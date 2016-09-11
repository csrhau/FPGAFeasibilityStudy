MANTEVOURL = https://mantevo.org/downloads/releaseTarballs/miniapps
CURL = curl -s --insecure

ARCHIVES += PathFinder/PathFinder_1.0.0.tgz

BMDIRS = $(patsubst %.tgz,%, $(patsubst %.tar.gz,%, $(ARCHIVES)))

.DEFAULT: all
.PHONY: all
all: $(BMDIRS)

%: %.tar.gz
	tar -zxvm -C $(dir $@) -f $<

%: %.tgz
	tar -zxvm -C $(dir $@) -f $<

PathFinder/PathFinder_1.0.0.tgz: | PathFinder
	 $(CURL) -o $@ $(MANTEVOURL)/$@

# Todo - wildcard over all archives $(dirname $x)
$(dir $(ARCHIVES)):
	mkdir -p $@

.PHONY: clean
clean:
	rm -rf $(dir $(ARCHIVES))
