# Discription
# openFoam8
Here is pimpleFoam files for passive scalar transport analysis basedon functinons models.

You donot need waste anymore time to fight with reactingFoam or buoyantPimpleFoam.

Maybe u have already know how to simulate the "passive scalar transport in transient turbulance" process, but the code I shared here just want to help the guys who is the first man need to do some research works in this field.
The only thing we need to do is add some code in the file——controlDict. This is really simple, bue if there have no help, we may still need waste one whole week to fight with that, Odamn, that feeling sooo bad.

# 文件简述
算例文件在openFoam8环境下使用
Win平台的OF4Win 20.09 和 ubuntu的openFoam8 均可运行，代码只在引入libsolverFunctionObjects动态库时存在微小差别（文件后缀不同）。

此算例的要点在于：基于“pimpleFoam & 内嵌functions模块"的湍流瞬态场中污染物扩散过程的求解，无需扒开C++求解器去添加代码，当然可能因我没做过C++项目，所以太菜。

因本人在此过程中走了极多的弯路，所以并不希望他人在此过程中承受没有必要的痛苦，与其在CFD_Online的淤泥里抓泥鳅，不如直接Ctrl_CV后去玩战地1，西奈会带给大家无限的快乐。
当然组中有前辈技术传承的诸位，以及可以直接手挫求解器大神，可以直接略过，这个算例只是为了帮助像我一样是组中第一个研究用openfoam搞瞬态湍流场中标量扩散的人。

# 文件要点
为解决在pimpleFoam模块下配置functions(scalarTransport)后，在fvOptions中定义标量源依然无法得到预期效果的情形：其中报错主要包括Source pollutantSource defined for field T but never used之类。
一般情况下，虽在fvOptions中配置k源可以正常运算，但是配置标量源(pimpleFoam-functions-scalarTransport)，就是没法算，可以说是求生不得求死不能。
本算例中，参考了uttamcadambi07的dafoam项目中的Discussions部分，将用于定义标量源数值大小的fvOptions集成到controlDict文件中的functions模块内，从而完成————不修改源码，在pimpleFoam实现求解固定位置标量源瞬态湍流扩散的目的。
其中，污染源空间区域设置，主要由topoSet文件实现。

# 随意吐槽
当然比较普遍的内容，deepseek都会告诉你，但是关于在openfoam8内如何在pinpleFoam实现固定浓度标量瞬态扩散仿真，它是真的不知道，或许以后就知道了。
希望遇到类似问题的诸位，以后可以少受点苦，或者早点定课题，有时间可以多看看理论和源码，直接上来搞，的确是非常的不好。
