CURL = curl -s --insecure

MODULE_LOCAL= provisioning/roles/environment_modules/files/modules-3.2.10.tar.gz
MODULE_REMOTE = http://heanet.dl.sourceforge.net/project/modules/Modules/modules-3.2.10/modules-3.2.10.tar.gz

.PHONY: all
all: downloads


.PHONY: downloads
downloads: $(MODULE_LOCAL)

$(MODULE_LOCAL):
	 $(CURL) -o $@ $(MODULE_REMOTE)


.PHONY: clean
clean:
	rm -f $(MODULE_LOCAL)
