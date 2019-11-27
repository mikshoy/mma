1.	Текст программы на Assembler
org 0x7c00
start:
	mov ah, 2
	mov al, 25
	mov ch, 0
	mov cl, 2
	mov dh, 0
	mov dl, 0x80
	mov bx, 0x8000
	int 0x13
	jmp 0x800:0
ret
2.	Текст программы на C/C++
asm(".code16gcc\n");
void setVMode(int mode);
void setChar(int x, int y, int text, int color);
int hitkey();

int start(){
	char choise1[] = "Hello";
	char choise2[] = "Study";
	char choise3[] = "Work";
	char choise4[] = "Rest";
	char choise5[] = "Bye";
	char text1[] = "Hi";
	char text2[] = "Labs";
	char text3[] = "Workout";
	char text4[] = "Games";
	char text5[] = "Noooo";
	int i;
		
	while(1){
		int point = 1;
		setVMode(3);
		int x = 20;
		for(i = 0; choise1[i]; i++){
			setChar(x, 3, choise1[i], 12);
			x++;
		}
		x = 20;
		for(i = 0; choise2[i]; i++){
			setChar(x, 4, choise2[i], 5);
			x++;
		}
		x = 20;
		for(i = 0; choise3[i]; i++){
			setChar(x, 5, choise3[i], 5);
			x++;
		}
		x = 20;
		for(i = 0; choise4[i]; i++){
			setChar(x, 6, choise4[i], 5);
			x++;
		}
		x = 20;
		for(i = 0; choise5[i]; i++){
			setChar(x, 7, choise5[i], 5);
			x++;
		}
			
		while(hitkey() != 28){
			switch(hitkey()){
				case 72:   1){
						x = 20;
						for(i = 0; choise1[i]; i++){
							setChar(x, 3, choise1[i], 5);
							x++;
						}
						x = 20;
						for(i = 0; choise5[i]; i++){
							setChar(x, 7, choise5[i], 12);
							x++;
						}
						point = 5;
					}
					else if(point == 2){
						x = 20;
						for(i = 0; choise2[i]; i++){
							setChar(x, 4, choise2[i], 5);
							x++;
						}
						x = 20;
						for(i = 0; choise1[i]; i++){
							setChar(x, 3, choise1[i], 12);
							x++;
						}
						point = 1;
					}
					else if(point == 3){
						x = 20;
						for(i = 0; choise3[i]; i++){
							setChar(x, 5, choise3[i], 5);
							x++;
						}
						x = 20;
						for(i = 0; choise2[i]; i++){
							setChar(x, 4, choise2[i], 12);
							x++;
						}
						point = 2;
					}
					else if(point == 4){
						x = 20;
						for(i = 0; choise4[i]; i++){
							setChar(x, 6, choise4[i], 5);
							x++;
						}
						x = 20;
						for(i = 0; choise3[i]; i++){
							setChar(x, 5, choise3[i], 12);
							x++;
						}
						point = 3;
					}
					else if(point == 5){
						x = 20;
						for(i = 0; choise5[i]; i++){
							setChar(x, 7, choise5[i], 5);
							x++;
						}
						x = 20;
						for(i = 0; choise4[i]; i++){
							setChar(x, 6, choise4[i], 12);
							x++;
						}
						point = 4;
					}
					break;
			case 80:if(point == 1){
					x = 20;
					for(i = 0; choise1[i]; i++){
						setChar(x, 3, choise1[i], 5);
						x++;
					}
					x = 20;
					for(i = 0; choise2[i]; i++){
						setChar(x, 4, choise2[i], 12);
						x++;
					}
					point = 2;
				}
				else if(point == 2){
					x = 20;
					for(i = 0; choise2[i]; i++){
						setChar(x, 4, choise2[i], 5);
						x++;
					}
					x = 20;
					for(i = 0; choise3[i]; i++){
						setChar(x, 5, choise3[i], 12);
						x++;
					}
					point = 3;
				}
				else if(point == 3){
					x = 20;
					for(i = 0; choise3[i]; i++){
						setChar(x, 5, choise3[i], 5);
						x++;
					}
					x = 20;
					for(i = 0; choise4[i]; i++){
						setChar(x, 6, choise4[i], 12);
						x++;
					}
					point = 4;
				}
				else if(point == 4){
					x = 20;
					for(i = 0; choise4[i]; i++){
						setChar(x, 6, choise4[i], 5);
						x++;
					}
					x = 20;
					for(i = 0; choise5[i]; i++){
						setChar(x, 7, choise5[i], 12);
							x++;
						}
						point = 5;
					}
					else if(point == 5){
						x = 20;
						for(i = 0; choise5[i]; i++){
							setChar(x, 7, choise5[i], 5);
							x++;
						}
						x = 20;
						for(i = 0; choise1[i]; i++){
							setChar(x, 3, choise1[i], 12);
							x++;
						}
						point = 1;
					}
					break;
				}
		}
		
		while (hitkey() != 1){
			switch(point){
				x = 20;
				case 1: setVMode(3);
					for(i = 0; text1[i]; i++){
						setChar(x, 5, text1[i], 12);
						x++;
					}
						break;
				case 2: setVMode(3);
					for(i = 0; text2[i]; i++){
					setChar(x, 5, text2[i], 12);
					x++;
					}
					break;
				case 3: setVMode(3);
					for(i = 0; text3[i]; i++){
						setChar(x, 5, text3[i], 12);
						x++;
					}
					break;
				case 4: setVMode(3);
					for(i = 0; text4[i]; i++){
						setChar(x, 5, text4[i], 12);
						x++;
					}
						break;
			}
			switch(point){
				case 5: setVMode(3);
					for(i = 0; text5[i]; i++){
						setChar(x, 5, text5[i], 12);
						x++;
					}
			break;
			}
		} 
	}
	return 0;
}

void setVMode(int mode){
	asm("mov ah, 0");
	asm("mov al, byte ptr[bp+8]");
	asm("int 0x10");
}

void setChar(int x, int y, int text, int color){
	char *p = 0xB8000;
	int offset = (y*320) + x*2;
	p+=offset;
	*p=(char)text;
	p++;
	*p=(char)color;
}

int hitkey(){
	int a=0;
	asm("mov ah, 0");
	asm("int 0x16");
	asm("mov byte ptr [bp-4], ah");
	return a;
}

3.	Параметры сборки/запуска проекта
1.	nasm -f bin lab1.asm -o lab1load.bin – программа загрузчик
2.	gcc -m32 -nostdlib -masm=intel lab1.c -o lab1.bin – основная программа
3.	objcopy lab1.bin -O binary
4.	Копируем в самое начало загрузчик. 511 и 512 байт устанавливаем значение 0х55 и 0хAA соответственно. Затем вставляем основную программу.
5.	qemu-system-i386 -vga std lab1.img – запуск

