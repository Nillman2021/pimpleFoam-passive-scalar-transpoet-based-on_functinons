# Discription
# openFoam8
Here is pimpleFoam files for passive scalar transport analysis basedon functinons models.

You donot need waste anymore time to fight with reactingFoam or buoyantPimpleFoam.

Maybe u have already know how to simulate the "passive scalar transport in transient turbulance" process, but the code I shared here just want to help the guys who is the first man need to do some research works in this field.
The only thing we need to do is add some code in the file——controlDict. This is really simple, bue if there have no help, we may still need waste one whole week to fight with that, Odamn, that feeling sooo bad.

# 文件简述
算例文件在openFoam8环境下使用
Win平台的OF4Win 20.09 和 ubuntu的openFoam8 均可运行，代码只在引入libsolverFunctionObjects动态库时存在微小差别（文件后缀不同）

此算例的要点在于：基于“pimpleFoam & 内嵌functions模块"的湍流瞬态场中污染物扩散过程的求解，无需扒开C++求解器去添加代码，当然可能因我没做过C++项目，所以太菜

因本人在此过程中走了极多的弯路，所以并不希望他人在此过程中承受没有必要的痛苦，与其在CFD_Online的淤泥里抓泥鳅，不如直接Ctrl_CV后去玩战地1，西奈会带给大家无限的快乐
当然组中有前辈技术传承的诸位，以及受挫求解器大神可以直接略过，这个算例只是为了帮助像我一样是组中第一个研究用openfoam搞瞬态湍流场中标量扩散的人
