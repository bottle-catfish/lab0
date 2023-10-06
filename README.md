# A Kernel Seedling
This kernel module counts the number of running processes and outputs it to the file /proc/count.

## Building
Use the following command to build the module : 
```shell
make
```
To clean the previous build use : 
```shell
make clean
```

## Running
To run, use the following command to insert the module into the kernel
```shell
sudo insmod proc_count.ko
```
You can then run the following to read the value of the number of processes running
```shell
cat /proc/count
```
When run on the virtual machine, I got 157 processes. 

## Cleaning Up
To remove the kernel module you can use the following : 
```shell
sudo rmmod proc_count
```

## Testing
```python
python -m unittest
```
Running python -m unittest showed that all 3 of my tests passed

Report which kernel release version you tested your module on
(hint: use `uname`, check for options with `man uname`).
It should match release numbers as seen on https://www.kernel.org/.

```shell
uname -r -s -v
```
Kernel Version : Linux 5.14.8-arch1-1 
