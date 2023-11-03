from building import *
import os

cwd = GetCurrentDir()
CPPPATH = []

src = Split('''
src/tm_stat.c
src/tm_model.c
src/tm_layers.c
src/tm_layers_O1.c
src/tm_layers_fp8.c
''')

CPPPATH += [cwd + '/src']
CPPPATH += [cwd + '/include']

if GetDepend(['R_TINYMAIX_USING_CIFAR10_SAMPLE']):
    src += ['examples/cifar10/cifar10.c']

if GetDepend(['R_TINYMAIX_USING_MBNET_SAMPLE']):
    src += ['examples/mbnet/mbnet.c']

if GetDepend(['R_TINYMAIX_USING_MNIST_SAMPLE']):
    src += ['examples/mnist/mnist.c']

if GetDepend(['R_TINYMAIX_USING_VWW_SAMPLE']):
    src += ['examples/vww/vww.c']

LOCAL_CFLAGS = '--gnu'

group = DefineGroup('r-tinymaix', src, depend = [''], CPPPATH = CPPPATH, LOCAL_CFLAGS = LOCAL_CFLAGS)
Return('group')