files = Program.cs \
		../libwasm/bin/flo/libwasm.flo

common_options = -asm-name=wasm-cat -asm-version=0.1.5.0 -Wall -Wextra

.PHONY: all exe flo clean
all: exe flo

exe: bin/clr/wasm-cat.exe
flo: bin/flo/wasm-cat.flo

clean:
	rm -rf bin/
	rm -rf obj/

include ../flame-make-scripts/use-ecsc.mk

bin/clr/wasm-cat.exe: $(files) | ecsc
	$(ECSC) $(files) -platform clr -o $@ -O3 $(common_options)

bin/flo/wasm-cat.flo: $(files) | ecsc
	$(ECSC) $(files) -platform ir -runtime clr -o $@ $(common_options)
