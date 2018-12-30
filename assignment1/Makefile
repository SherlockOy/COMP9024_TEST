objects = listIteratorInt.o testListIteratorInt.o
test : $(objects)
	gcc -Wall -Werror -g -o murui_test.out $(objects) -lcheck

testListIteratorInt.o: testListIteratorInt.c

listIteratorInt.o : listIteratorInt.c  listIteratorInt.h

clean:
	rm *.o test