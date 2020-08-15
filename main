#include <stdio.h>
#include <signal.h>
#include <stdlib.h>
#include <unistd.h>
#include <string.h>

void alarm_handler(int);
void controlC_handler(int);

void main(){
	char user[25];//setting user input.
	
	signal (SIGALRM, alarm_handler);
	signal (SIGINT, controlC_handler);

	while(1){
		alarm(5);
		//prompting question:
		printf("\n What is your username? : ");
		//getting user input
		scanf("%s", user);
			
		//quitting
		if(strcmp(user,"exit") == 0 || strcmp(user,"quit")== 0){
			printf("\n Goodbye!");
			exit(0);
		}
		printf("\n Your username is: %s", user);		
	}	
}

void alarm_handler(int Alarm){
	printf("\n Times up!");
	sleep(1);//suspends execution for one second.
	printf("\n What is your usernane? :");
	//clears the  output buffer and moves the data to the console.
	fflush(stdout);
	alarm(5);//resetting alarm
	return;

}
void controlC_handler(int quit){
	//if control c was entered as an attempt to exit.
	printf("\n Please enter 'quit' or 'exit' to end. ");
	printf("\n What is your username? : ");//reprompting user
	fflush(stdout);

	return;
}
