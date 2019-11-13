# CISC
## 计算机组成原理课设 CISC核心代码
### 设计一台嵌入式CISC模型机
1. 课程设计选题：任意输入5个整数，输出所有正数的平方和。
2. 汇编代码  
：       MOV R3,0H ;R0累计和
   MOV R1,5H ;R1计数器，从5开始降到0，计数5次
L1:TEST R1   ;判断R1为0则跳转
   JZ L2     ;跳转L2
   INT R2    ;R2输入数据
   TEST R2   ;测试R2是否为负数
   JB L1     ;如果小于0，跳转L1继续输入
   MUL R2,R2 ;R2自乘
   ADD R2,R3 ;R3=R3+R2
   DEC R1    ;计数减1
   JMP L1  
L2:OUT R3    ;输出累加和
   JMP L2
