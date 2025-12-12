EJECUTABLE = pruebas.exe
MAIN = pruebas.c

#Incluye las librerias que necesites, se incluye el .c
#---------------------------------
LIB_1 = graficos.c
LIB_2 = serial.c
LIB_3 = simplecontroller.c
#---------------------------------
#Escoge el compilador que necesites
#---------------------------------
COMPILER = gcc
#---------------------------------
#Añade las banderas que necesites
#---------------------------------
FLAG_1 = -mwindows
#---------------------------------

#Coloca los archivos .o de esas mismas librerias
OBJ = graficos.o serial.o simplecontroller.o 
#Pasa los archivos .o a .d, para que make pueda organizarse 
DEPS = $(OBJ:.o=.d)

run: $(EJECUTABLE)
	./$(EJECUTABLE)

$(EJECUTABLE): $(MAIN) $(OBJ)
	$(COMPILER) $(MAIN) $(OBJ) -o $(EJECUTABLE) $(FLAG_1)
#El %.o: %.c crea una regla general que para todo archivo .c se pueda generar un .o
#MDD crea un archivo .d con el que revisamos todas las dependencias .h
%.o: %.c
	$(COMPILER) -c -MD $< -o $@
#Incluye los archivos .d si es que existen, el - evita errores
-include $(DEPS)
#Elimina los archivos temporales
clean:
	rm -f *.o $(EJECUTABLE)
