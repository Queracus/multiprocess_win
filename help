import time
from multiprocessing import Process

def ask_user():
    start = time.time()
    user_input=input('enter your name: ')
    greet = f'Hello, {user_input}'
    print(greet)
    print(f'ask_user, {time.time() - start}')

def complex_calc():
    start = time.time()
    print('Started calculating....')
    [x**2 for x in range(20000000)]
    print(f'complex_calc, {time.time() - start}')

start = time.time()
ask_user()
complex_calc()
print(f'Single thread total time: {time.time() - start}')


#-----------------------------------------


process = Process(target=complex_calc)
process2 = Process(target=complex_calc)

if __name__ == "__main__":
    process.start()
    process2.start()

    start = time.time()

    process.join()
    process2.join()

    print(f'2 process total time is: {time.time() - start}')
    
    
OUTPUT I GET:
enter your name: x
Hello, x
ask_user, 1.9884631633758545
Started calculating....
complex_calc, 4.874430894851685
Single thread total time: 6.862894058227539
enter your name: enter your name: x
Hello, x
ask_user, 1.7962534427642822
Started calculating....
complex_calc, 4.89444899559021
Single thread total time: 6.690702438354492
Started calculating....
complex_calc, 4.891441822052002

processes keep running and dont shut off
