# GabrielKernel
<!-- ОПИСАНИЕ -->
## Описание

Ядро, совместимое с x86 (linux)


<!-- Запуск -->
## Запуск

Для запуска лучше всего использовать виртуальную машину на KDE

Перед запуском ядра:
1. Скачать архив
2. Открыть терминал
3. Установить команду nasm
   ```sh
   sudo apt install nasm
   ```
4. Установить команду gcc
   ```sh
   sudo apt install gcc
   ```
5. Установить qemu
   ```sh
   sudo apt install qemu-system-x86
   ```

1. Ядро без ввода:
   1.1 Открыть терминал в папке "kernel-noinput"
   1.2 Прописать:
       ```sh
       $ nasm -f elf32 kernel.asm -o kasm.o
       ```
       ```sh
       $ gcc -m32 -c kernel.c -o kc.o
       ```
       ```sh
       $ ld -m elf_i386 -T link.ld -o kernel kasm.o kc.o
       ```
       ```sh
       qemu-system-i386 -kernel kernel
       ```

2. Ядро с вводом:
   2.1 Открыть терминал в папке "kernel-yesinput"
   2.2 Прописать:
       ```sh
       $ nasm -f elf32 kernel.asm -o kasm.o
       ```
       ```sh
       $ gcc -fno-stack-protector -m32 -c kernel.c -o bin/kc.o
       ```
       ```sh
       $ ld -m elf_i386 -T link.ld -o kernel kasm.o kc.o
       ```
       ```sh
       qemu-system-i386 -kernel kernel
       ```


<!-- КОНТАКТЫ -->
## Контакты

Email проекта: 11802@student.spb-rtk.ru
