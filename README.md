#include <stdio.h>
/*Vu Nguyen
  Exam 4
  4/20/2023
  Perform the calculations for a class experiment 
*/
#define GRAVITY 9.8 // define constant for gravity

int main(){
     double mass[12]; // create an array to store the mass of 12 objects
	 double weight[12]; // create an array to store the weight of 12 objects
	 int i;
	 // prompt the user to input the mass of each object 
	 printf("Enter the mass of each object (between 1.5 to 5 lbs):\n");
	 
	 // loop through the array to populate with the mass of each object 
	 for(i=0; i < 12; i++) {
	 	printf("Object %d: ", i+1);
	 	scanf("%lf", &mass[i]);
	 	
	 	// validate the input to ensureno erroneous mass can be inputted
	 	if (mass[i] < 1.5 || mass[i] > 5){
	 		printf("Error: Mass should be between 1.5 to 5 lbs.\n");
	 		i--;// go back to the previous object 
		 }
	 }
	 
	// calculate the weight of eachobject and store it in the weight array
	 for (i = 0; i < 12; i++) {
	 	weight[i] = mass[i] * GRAVITY;
}
	 	
	 	// display the results of the experiment in a tabular manner
	 printf("\nResults:\n");
	 printf("Object\tMass (lbs)\tWeight (N)\n");
	 for (i = 0; i < 12; i++) {
	 	printf("%d\t%.2lf\t\t%.2lf\n", i+1, mass[i], weight[i]);
	 }
	 // print out the sample output
	 printf("\nSample output:\n");
	 printf("Object 1: mass 1.5 lbs, weight %.21f N\n", mass[0]*GRAVITY);
	 printf("Object 6: mass 3.8 lbs, weight %.21f N\n", mass[5]*GRAVITY);
	 
	 return 0;
}
