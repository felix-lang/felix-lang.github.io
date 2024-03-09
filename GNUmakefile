pretty: 
	env DYLD_LIBRARY_PATH=${LD_LIBRARY_PATH} flx_pretty --outdir=web openrecursion.fdoc
	env DYLD_LIBRARY_PATH=${LD_LIBRARY_PATH} flx_pretty --outdir=web embedc.fdoc
	env DYLD_LIBRARY_PATH=${LD_LIBRARY_PATH} flx_pretty --outdir=web corout.fdoc
	env DYLD_LIBRARY_PATH=${LD_LIBRARY_PATH} flx_pretty --outdir=web views.fdoc
	env DYLD_LIBRARY_PATH=${LD_LIBRARY_PATH} flx_pretty --outdir=web ../felix/src/packages/lists.fdoc

tut:
	for file in /Users/skaller/felix/src/web/tut/*.fdoc; do \
	  env DYLD_LIBRARY_PATH=${LD_LIBRARY_PATH} flx_pretty --outdir=web "$${file}"; \
	  done
	for file in web/*.html; do sed -i -e s/fdoc/html/g $${file}; done
	rm web/*.html-e


packages:
	for file in /Users/skaller/felix/src/packages/*.fdoc; do \
	  env DYLD_LIBRARY_PATH=${LD_LIBRARY_PATH} flx_pretty --outdir=packages "$${file}"; \
	  done
	for file in packages/*.html; do sed -i -e s/fdoc/html/g $${file}; done
	rm -rf packages/*.html-e

extract:
	flx_iscr embedc.fdoc
	flx_iscr corout.fdoc
	flx_iscr openrecursion.fdoc

 
test:
	flx --regex='examples/.*\.flx'

deploy:
	git add examples/*/*.flx
	git commit -a
	git push

all: pretty extract test deploy

.PHONY: packages
