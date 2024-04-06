# 自动控制原理

学习的是《Control Systems Engineering》。

## 第一章 Introduction

Review Questions:

1. Name three applications for feedback control systems.
   1. PLL: phase lock loop;
   2. ABS: anti-lock brake system;
   3. ??
2. Name three reasons for using feedback control systems and at least one reason for not using them.
   1. Yes: for precise output; for turbulence proof; ???
   2. No: too expensive, too complex;
3. Give three examples of open-loop systems.
   1. DC motor;
   2. RC Low Pass filter(passive filter);
   3. inertia supported between two bearings(???)
4. Functionally, how do closed-loop systems differ from open-loop systems?
   1. I think it is the feedback: Close-loop systems compensate for disturbance and bias by measuring the response, comparing it to the input response(the desired output), and then correcting the output response.
5. State one condition under which the error signal of a feedback control system would not be the difference between the input and the output.
   1. ???
6. If the error signal is not the difference between input and output, by what general name can we describe the error signal?
   1. ???
7. Name two advantages of having a computer in the loop.
   1. The computer can calculate and compansate very fast.
   2. Multiple subsystems can time share the controller.
   3. Any adjustments to the controller can be implemented with simply software changes.
8. <font face="黑体" color=red>Name the three major design criteria for control systems.</font>
   1. Stability
   2. transient response
   3. steady-state error
9. Name the two parts of a system’s response.
   1. transient
   2. Steady-state
10. Physically, what happens to a system that is unstable?
    1. It follows a growing transient response until the steady-state response is no longer visible. The system will either destroy itself, reach an equilibrium state because of saturation in driving amplifiers, or hit limit stops.
11. Instability is attributable to what part of the total response?
    1. Natural response????
12. Describe a typical control system analysis task.
    1. <font face="黑体" color=red> Determine the transient response performance of the system.</font> But why?
13. Describe a typical control system design task.
    1. Determine system parameters to meet the transient response specifications for the system.
14. Adjustments of the forward path gain can cause changes in the transient response.
    1. True.
15. Name three approaches to the mathematical modeling of control systems.
    1. 微分方程
    2. 状态空间方程
    3. 传输函数。
16. Briefly describe each of your answers to Question 15.
    1. differential equations: Modeling a system with its differential equation
    2. State-space: representation of an nth order differential equation as n simultaneous first-order differential equations(不懂，得学习)。
    3. Transfer function - the Laplace transform of the differential equation

疑问：

全响应=稳态响应+暂态响应=零输入响应+零初始响应=自然响应+受迫响应。

稳态响应+暂态响应： 按照最终状态分类
零输入响应+零初始响应： 按照初始状态和控制输入
自然响应+受迫响应： 考虑是否对系统施加影响

1. 全响应：系统在某个初始状态x0下，在给定输入信号u的作用下，系统状态x随时间的变化称为全响应。任何情况下，观察到的系统的响应都是全响应。
2. 零输入响应（和初始状态有关）：系统在某个初始状态x0下，不受控制信号u的作用（也即u始终为0）时，系统状态随时间的变化称为零输入响应。
3. 零初始响应（零状态响应）（和控制输入有关）：系统初始状态为0时，在给定控制信号u的作用下，系统状态x随时间的变化称为零状态响应。设置系统初始状态为0，设置控制信号为u，则此时的全响应就是对应控制信号u的零状态响应。
4. 稳态响应（和初始状态和控制信号u有关）： 在给定系统初始状态和给定控制信号u的作用下，系统状态最终达到稳态（定值、周期值）等，这个稳定的信号就是稳态响应。
5. 暂态响应（和初始状态和控制信号u有关）： 虽然系统最终将达到稳态，但是总是需要一定时间调整到稳态信号。暂态响应描述了这个调整的过程，也就是暂态响应=全响应-稳态响应。
6. 自然响应： 不对系统施加影响时，系统的响应为自然响应。实际上，也就是零输入响应，不施加影响，就是控制输入为0.
7. 受迫响应：如何定义？？？

## 参考及引用

[1] Control Systems Engineering 7th Ed - Nise.
[2] Control Systems Engineering Solutions. <https://www.chegg.com/homework-help/control-systems-engineering-7th-edition-chapter-1-solutions-9781118170519>
