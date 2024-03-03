
INCLUDE = "/opt/cpm/libraries/pmax-packages"
ASMFILE = "Primes"
MACHINEFILE = "Primes.bbx"
PROFILECOMPILER = #--profile
VIEWEXECUTION = #--view-short
PRINTASSEMBLERSTATS = #--print-stats
EMITINTERMEDIATE = #--emit-offsets --emit-tac --emit-pil
EMITINDICES = #--emit-indices

# Increased instruction count bound by a factor of 100x compared to default.
MAXINSTRUCTIONS = 100000000

INCLUDECOMMENTS = #--include-comments

all:
	@echo "Building ..."
	@pmax build --target-name $(ASMFILE) --include $(INCLUDE) $(PROFILECOMPILER) $(EMITINTERMEDIATE) $(INCLUDECOMMENTS)
	@bbasm assemble _targets/$(ASMFILE).bba _targets/$(MACHINEFILE) $(EMITINDICES) $(PRINTASSEMBLERSTATS)
	@echo "Running ..."
	@bbvm run _targets/$(MACHINEFILE) $(VIEWEXECUTION) --max-instructions $(MAXINSTRUCTIONS)
