# projeto-gest-o-de-estoque-
ferramenta para Gestão de Estoque 
// Projeto Gestão de Estoque // Cristian Diego De Mattos//

#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#define MAX_ITEMS 100 // define a capacidade maxima de armazenamento //
struct Item{
char name[50];
int quantity;
float price;};
struct Item stock[MAX_ITEMS];   //estrutura de armazenamento //
int num_items = 0;  // intens armazenados //
void
add_item (){
if (num_items >= MAX_ITEMS){  // Define a capacidade maxima de armazenamento //
printf ("numero maximo de itens atingido\n");
return;}
struct Item item;
printf ("Digite o nome do item: ");
scanf ("%s", item.name);
printf ("Insira a quantidade do item: ");
scanf ("%d", &item.quantity);
printf ("Insira o preço do item: ");
scanf ("%f", &item.price);
stock[num_items++] = item;} 
void
remove_item (){
  char name[50];
printf ("Insira o nome do item a ser removido: ");
scanf ("%s", name);
int i, index = -1;
for (i = 0; i < num_items; i++){
if (strcmp (stock[i].name, name) == 0){
index = i;
break;}}
if (index == -1){
printf ("Erro: Item não encontrado \n");
return;}
for (i = index; i < num_items - 1; i++){
stock[i] = stock[i + 1];}
num_items--;}
void
display_stock (){
int i;
printf ("%-20s %-10s %-10s\n", "nome", "quantidade", "preço");
for (i = 0; i < num_items; i++){
printf ("%-20s %-10d %-10.2f\n", stock[i].name, stock[i].quantity,
stock[i].price);}}
void
search_item (){
char search_name[50];
printf ("Digite o nome do item a ser pesquisado: ");
scanf ("%s", search_name);
int found = 0;
for (int i = 0; i < num_items; i++)    {
if (strcmp (stock[i].name, search_name) == 0)	{
printf ("%-20s %-10d %-10.2f\n", stock[i].name, stock[i].quantity,
stock[i].price);
found = 1;
break;}}
if (!found){
printf ("Item não encontrado.\n");}}
int
main (){
int choice;
do{
printf ("\nSistema de gerenciamento de estoque\n");	// PAGINA DO MENU //
printf ("1. Adicionar Item\n");
printf ("2. Remover Item\n");
printf ("3. Exibir Estoque\n");
printf ("4. Pesquisar Item\n");
printf ("5. sair \n");
printf ("Digite sua escolha: ");
scanf ("%d", &choice);
switch (choice){
case 1:
add_item ();
break;
case 2:
remove_item ();
break;
case 3:
display_stock ();
break;
case 4:
search_item (0);
case 5:
exit (0);
default:
printf ("Escolha invalida\n");}}
while (choice != 4);
return 0;}
