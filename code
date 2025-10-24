#include <iostream>
#include <unistd.h>
#include <sys/wait.h>
#include <sys/types.h>
using namespace std;

int status;
void FindError(){

         if (WIFSIGNALED(status) == 1) {
         if (WTERMSIG(status) == 11) {
         cout << "segmentation violation\n";
         }
         else if (WTERMSIG(status) == 8) {
         cout << "program crashed due to division\>
         }
         else {
         cout << "program crashed due to signal\n";
         }
         }
        else if (WIFEXITED(status) == 0) {
         cout << "program crashed\n";}
         else {
         cout << "program succeeded\n";
        }
        }

int main(int argc, char *argv[])
{
        pid_t  program = fork();

        if(program == 0){
        execvp(argv[1] ,&argv[1]);
        }
        else if(program > 0){
        waitpid(program, &status ,0);
        FindError();
        }
  return 0;
}