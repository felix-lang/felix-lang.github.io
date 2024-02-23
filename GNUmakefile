pretty: 
	env DYLD_LIBRARY_PATH=${LD_LIBRARY_PATH} flx_pretty embedc.fdoc
	env DYLD_LIBRARY_PATH=${LD_LIBRARY_PATH} flx_pretty corout.fdoc

extract:
	flx_iscr embedc.fdoc
	flx_iscr corout.fdoc

 
test:
	flx --regex='examples/.*\.flx'

deploy:
	git add examples/*/*.flx
	git commit -a
	git push

all: pretty extract test deploy

