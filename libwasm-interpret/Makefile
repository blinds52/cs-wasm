files = \
	DefaultInstructionInterpreter.cs \
	DelegateFunctionDefinition.cs \
	FunctionDefinition.cs \
	FunctionTable.cs \
	IImporter.cs \
	InstructionInterpreter.cs \
	InterpreterContext.cs \
	LinearMemory.cs \
	ModuleInstance.cs \
	OperatorImpls.cs \
	PredefinedImporter.cs \
	SpecTestImporter.cs \
	ThrowFunctionDefinition.cs \
	TracingInstructionInterpreter.cs \
	ValueHelpers.cs \
	Variable.cs \
	WasmFunctionDefinition.cs \
	BaseRuntime/TerminalRuntime.cs

libraries = ../libwasm-core/bin/flo/libwasm-core.flo

common_options = -asm-name=libwasm-interpret -asm-version=0.1.5.0 -Wall -Wextra

.PHONY: all flo clean
all: flo

flo: bin/flo/libwasm-interpret.flo

clean:
	rm -rf bin/
	rm -rf obj/

include ../flame-make-scripts/use-ecsc.mk

bin/flo/libwasm-interpret.flo: $(files) $(libraries) | ecsc
	$(ECSC) $(files) -platform ir -runtime clr -o $@ $(common_options) --libs $(libraries)
