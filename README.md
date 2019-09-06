# AI智能换脸
<p align="center">
  <a href="https://faceswap.dev"><img src="https://i.imgur.com/zHvjHnb.png"></img></a>
<br />FaceSwap是一个利用深度学习来识别和交换图片和视频中的人脸的工具.
</p>
<p align="center">
<img src = "https://i.imgur.com/nWHFLDf.jpg"></img>
</p>

<p align="center">
<a href="https://www.patreon.com/bePatron?u=23238350"><img src="https://c5.patreon.com/external/logo/become_a_patron_button.png"></img></a>
</p>
<p align="center">
  <a href="https://www.youtube.com/watch?v=r1jng79a5xc"><img src="https://img.youtube.com/vi/r1jng79a5xc/0.jpg"></img></a>
<br /><br />詹妮弗·劳伦斯/史蒂夫·巴斯米·法斯瓦普使用恶棍的模型
</p>

[![Build Status](https://travis-ci.org/deepfakes/faceswap.svg?branch=master)](https://travis-ci.org/deepfakes/faceswap)

在开始之前，请确保安装[INSTALL.md](INSTALL.md

- [deepfakes_faceswap](#deepfakesfaceswap)
- [Manifesto](#manifesto)
  - [FaceSwap has ethical uses.](#faceswap-has-ethical-uses)
- [How To setup and run the project](#how-to-setup-and-run-the-project)
- [Overview](#overview)
  - [Extract](#extract)
  - [Train](#train)
  - [Convert](#convert)
  - [GUI](#gui)
- [General notes:](#general-notes)
- [Help I need support!](#help-i-need-support)
  - [Discord Server](#discord-server)
  - [FaceSwap Forum](#faceswap-forum)
- [Donate](#donate)
  - [Patreon](#patreon)
  - [One time Donations](#one-time-donations)
    - [@torzdf](#torzdf)
    - [@andenixa](#andenixa)
    - [@kvrooman](#kvrooman)
- [How to contribute](#how-to-contribute)
  - [For people interested in the generative models](#for-people-interested-in-the-generative-models)
  - [For devs](#for-devs)
  - [For non-dev advanced users](#for-non-dev-advanced-users)
  - [For end-users](#for-end-users)
  - [For haters](#for-haters)
- [About github.com/deepfakes](#about-githubcomdeepfakes)
  - [What is this repo?](#what-is-this-repo)
  - [Why this repo?](#why-this-repo)
  - [Why is it named 'deepfakes' if it is not /u/deepfakes?](#why-is-it-named-deepfakes-if-it-is-not-udeepfakes)
  - [What if /u/deepfakes feels bad about that?](#what-if-udeepfakes-feels-bad-about-that)
- [About machine learning](#about-machine-learning)
  - [How does a computer know how to recognize/shape faces? How does machine learning work? What is a neural network?](#how-does-a-computer-know-how-to-recognizeshape-faces-how-does-machine-learning-work-what-is-a-neural-network)

# 声明

## FaceSwap 需要有道德的使用者.

当faceswapping首次开发并发布时，这项技术是开创性的，它是人工智能发展的一大步. 在学术界之外，它也完全被忽略了，因为代码是混乱和零碎的. 它需要对复杂的人工智能技术有一个全面的了解，并花费了大量的努力来解决它. 直到有一个人把它们组合成一个整体。它运行起来，工作起来，就像互联网上出现的新技术一样，它很快就被用来创建不合适的内容。尽管该软件最初的使用不当，但它是第一个任何人都可以通过实验下载、运行和学习的人工智能代码，而不需要数学、计算机理论、心理学等博士学位。在“深度造假”之前，这些技术就像巫术一样，只有那些能够理解深奥而又无穷复杂的书籍和论文中所描述的所有内部工作原理的人才会使用.

"Deepfakes" 改变了这一切，任何人都可以参与人工智能的开发。对于我们开发人员来说，这段代码的发布提供了一个极好的学习机会。它使我们能够建立在他人开发的想法之上，与各种熟练的程序员合作，在学习新技能的同时进行人工智能实验，并最终为一项新兴技术做出贡献，随着技术的进步，这种技术只会得到更主流的应用.

是否有一些人在用类似的软件做可怕的事情?是的。正因为如此，开发商一直遵循严格的道德标准。我们中的许多人甚至不使用它来创建视频，我们只是修改代码，看看它能做什么。遗憾的是，媒体只关注这种软件的不道德使用。不幸的是，这就是它最初如何向公众公开的本质，但它并不能代表为什么要创建它，我们现在如何使用它，或者我们在未来看到了什么。就像任何技术一样，它可以被用于好的方面，也可以被滥用。我们的目的是开发FaceSwap，使其滥用的可能性降到最低，同时最大限度地发挥其作为学习、实验工具的潜力，当然，还有作为合法的faceswapping工具的潜力.

我们不想诋毁名人或贬低任何人。我们是程序员，我们是工程师，我们是好莱坞特效艺术家，我们是活动家，我们是爱好者，我们是人类。为了达到这个目的，我们觉得是时候对这个软件做一个标准的说明了.

- FaceSwap 不是用来创建不合适的内容的。
- FaceSwap不能在未经同意或意图隐藏其用途的情况下改变面部。
- FaceSwap并非用于任何非法、不道德或可疑的目的。
- FaceSwap的存在是为了试验和发现人工智能技术，用于社会或政治评论，电影，以及任何数量的道德和合理的用途。

我们非常困扰的事实，FaceSwap可以用于不道德和不体面的事情。然而，我们支持开发可在道德上使用的工具和技术，并为任何希望亲自学习人工智能的人提供人工智能方面的教育和经验。我们将对任何出于不道德目的使用本软件的人采取零容忍的态度，并将积极劝阻任何此类使用。

# 设置和运行项目
FaceSwap是一个Python程序，可以在多个操作系统上运行，包括Windows、Linux和MacOS。

[INSTALL.md](INSTALL.md) 参阅完整的安装说明。你将需要一个现代GPU与CUDA支持最佳性能。部分支持AMD gpu。

# 概述
项目有多个入口点。你必须:
-收集照片和/或视频
- **Extract**
- **Train** *从照片/视频中提取的人脸模型
- **Convert**您的源代码与模型


参阅 [USAGE.md](USAGE.md) 以获得更详细的说明。

## Extract
从安装文件夹中运行`python faceswap.py extract`。这将采取照片从`src`文件夹和提取的面孔到`extract`文件夹。

## Train
从安装文件夹中运行`python faceswap.py train`。这将从两个包含两张面孔照片的文件夹中拍摄照片，并训练一个模型，该模型将保存在`models`文件夹中。

## Convert
从安装文件夹中运行`python faceswap.py convert`。这将从“原始”文件夹中拍摄照片，并将新面孔应用到`modified`文件夹中。

## GUI
另外，您可以通过运行来运行GUI `python faceswap.py gui`

# 注意:
- 所有提到的脚本都有`-h`/`--help` 选项，它们的参数都是可以接受的。你懂得，小屌丝！

另:有一个视频转换工具。这可以通过运行`python tools.py effmpeg -h`。或者，您可以使用[ffmpeg](https://www.ffmpeg.org)将视频转换为照片、处理图像，并将图像转换回视频。


**一些技巧:**
重用现有的模型比从零开始训练要快得多。
如果没有足够的训练数据，就从长相相似的人开始，然后转换数据。

