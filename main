#include <iostream>
#include <fstream>
#include <cstring>
using namespace std;

int main(int argc, char**argv)
{
	int symbol_count = 0, CalcNumber;
	ofstream out("Results.txt");
	char* numbers = argv[1];
	symbol_count = strlen(numbers);
	if (argc < 2)
	{
		cout << "Missing arguments.\n";
		return 0;
	}
	__asm
	{
		push eax
		push ebx
		push ecx
		push edx

		xor eax, eax
		mov ebx, numbers

		my_loop:
		mov cl, byte ptr[ebx]
		cmp cl, 0
		jz my_end
		sub cl, '0'
		imul eax, 10
		add eax, ecx
		inc ebx
		jmp my_loop

		my_end:
		mov [CalcNumber], eax

		pop edx
		pop ecx
		pop ebx
		pop eax
	};
	
	cout << "Converted number : " << CalcNumber << endl;
	return 0;
}
