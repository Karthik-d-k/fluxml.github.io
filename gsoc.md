---
layout: page
title: Google Summer of Code
---

# Google Summer of Code Projects

Flux usually takes part in [Google Summer of Code](https://summerofcode.withgoogle.com), as part of the wider Julia organisation. We follow the same [rules and application guidelines](https://julialang.org/jsoc/guidelines/) as Julia, so please check there for more information on applying. Below are a set of ideas for potential projects (though you are welcome to explore anything you are interested in).

Flux projects are typically very competitive; we encourage you to get started early, as successful students typically have early PRs or working prototypes as part of the application. It is a good idea to simply start contributing via issue discussion and PRs and let a project grow from there; you can take a look at [this list of issues](https://github.com/issues?utf8=✓&q=is%3Aopen+archived%3Afalse+user%3AFluxML+label%3A%22help+wanted%22) for some starter contributions.

### Port ML Tutorials

There are many high-quality open-source tutorials and learning materials available, for example from PyTorch and fast.ai. We'd like to have Flux ports of these that we can add to the model zoo, and eventually publish to the Flux website.

Mentors: [Dhairya Gandhi](https://github.com/DhairyaLGandhi/).

### FermiNets: Generative Synthesis for Automating the Choice of Neural Architectures

The application of machine learning requires an understanding a practictioner to optimize a neural architecture for a given problem, or does it? Recently techniques in automated machine learning, also known as AutoML, have dropped this requirement by allowing for good architectures to be found automatically. One such method is the [FermiNet](https://arxiv.org/abs/1809.05989) which employs generative synthesis to give a neural architecture which respects certain operational requirements. The goal of this project is to implement the FermiNet in Flux to allow for automated sythesis of neural networks.

Mentors: [Chris Rackauckas](https://github.com/ChrisRackauckas) and [Dhairya Gandhi](https://github.com/DhairyaLGandhi/).

### Differentiable Rendering [HARD]

Expected Outcome: This is motivated to create SoftRasterizer/DiB-R based projects. We already have RayTracer.jl which is motivated by OpenDR. (Of course, if someone wants to implement NERF - like models they are most welcome to submit a proposal). We would ideally target at least 2 of these models.

Skills: GPU Programming, Deep Learning, (deep) familiarity with the literature, familiarity with defining (a lot of) Custom Adjoints

Mentors: [Dhairya Gandhi](https://github.com/DhairyaLGandhi/), [Avik Pal](https://github.com/avik-pal)

### Core Development [MEDIUM]

Expected Outcomes:

* Some of the functions require custom adjoints for speedup
* Functions require GPU kernels. Some of these are of common interest to the community like – knn, etc.
* Benchmarking with Tensorflow Graphics and Pytorch3D. We already have the scripts for kaolin, need to extend that.
* Most of these problems are listed as issues in the main repo.

Skills: GPU Programming, Deep Learning, familiarity with defining (a lot of) Custom Adjoints

Mentors: [Dhairya Gandhi](https://github.com/DhairyaLGandhi/)

### FastAI.jl Development

**Difficulty:** Medium

In this project, you will assist the [ML community team](https://julialang.zulipchat.com/#narrow/stream/237432-ml-ecosystem-coordination) with building FastAI.jl on top of the existing JuliaML + FluxML ecosystem packages. The primary goal is to create an equivalent to docs.fast.ai. This will require building the APIs, documenting them, and creating the appropriate tutorials. Some familiarity with the following Julia packages is preferred, but it is not required:

* [MLDataPattern.jl](https://github.com/JuliaML/MLDataPattern.jl.git)
* [FluxTraining.jl](https://github.com/lorenzoh/FluxTraining.jl.git)
* [DataAugmentation.jl](https://github.com/lorenzoh/DataAugmentation.jl)

A stretch goal can include extending FastAI.jl beyond its Python-equivalent by leveraging the flexibility in the underlying Julia packages. For example, creating and designing abstractions for distributed data parallel training.

**Skills:** Familiarity with deep learning pipelines, common practices, Flux.jl, and MLDataPattern.jl

Mentors: [Kyle Daruwalla](https://github.com/darsnack)

### Differentiable Computer Vision [HARD]

Expected Outcome:

Create a library of utliity functions that can consume Julia's Imaging libraries to make them differentiable. With Zygote.jl, we have the platform to take a general purpose package and apply automatic differentiation to it. This project is motivated to use existing libraries that offer perform computer vision tasks, and augment them with AD to perform tasks such as homography regression.

Skills: Familiarity with automatic differentiation, deep learning, and defining (a lot of) Custom Adjoints

Mentors: [Dhairya Gandhi](https://github.com/DhairyaLGandhi/)

### Make the Model-Zoo Robust

The model zoo has been a great resource for folks starting with Flux and machine learning in general. This time, we want to make the zoo significantly more useful. With Artifacts, we can have the models be completely reusable, and have high quality trained models availiable trivially. This would involve training the existing models and making the weights available through artifacts. We would also want to have ways to verify that the models perform well on the test datasets. For some more insight, we are looking out for more [Metalhead.jl](https://github.com/FluxML/Metalhead.jl) kind of workflows with a reference to how to use them in the zoo, plus finding high quality pretrained weights for the models, that have been verified to give the expected results, including numerical debugging.

Mentors: [Dhairya Gandhi](https://github.com/dhairyagandhi96/), [Elliot Saba](https://github.com/staticfloat).

### CUDA Hacking

Are you a performance nut? Help us implement cutting-edge CUDA kernels in Julia for operations important across deep learning, scientific computing and more. We also need help developing our wrappers for machine learning, sparse matrices and more, as well as CI and infrastructure. Contact us to develop a project plan.

Mentors: [Tim Besard](https://github.com/maleadt), [Mike Innes](https://github.com/MikeInnes).

### Reinforcement Learning Environments

Develop a series of reinforcement learning environments, in the spirit of the [OpenAI Gym](https://gym.openai.com). Although we have wrappers for the gym available, it is hard to install (due to the Python dependency) and, since it's written in Python and C code, we can't do more interesting things with it (such as differentiate through the environments). A pure-Julia version that supports a similar API and visualisation options would be valuable to anyone doing RL with Flux.

Mentors: [Dhairya Gandhi](https://github.com/DhairyaLGandhi/), [Elliot Saba](https://github.com/staticfloat).

### Model Zoo on TPU

Julia has experimental support for executing code on TPUs (https://github.com/JuliaTPU/XLA.jl) TPUs enable training cutting edge machine larning models written using Flux. However, TPUs are not able to execute arbitrary code and thus often require individual attention to fix new patterns in XLA.jl or other packages. Additionally, the performance characteristics of the TPU hardware are quite unlike that of CPU or even GPU and models may thus require TPU-specific adjustments to achieve peak performance. Lastly, the speed of TPUs presents signficant challenges to data input pipelines even at single-TPU levels of performance. Having a wide set of models available that are tuned for TPU will aid in finding common abstractions for models independent of hardware.

Mentors: [Keno Fischer](https://github.com/Keno)

### Benchmarks

A benchmark suite would help us to keep Julia's performance for ML models in shape, as well as revealing opportunities for improvement. Like the model-zoo project, this would involve contributing standard models that exercise common ML use case (images, text etc) and profiling them. The project could extend to include improving performance where possible, or creating a "benchmarking CI" like Julia's own [nanosoldier](https://github.com/JuliaCI/Nanosoldier.jl).

Mentors: [Dhairya Gandhi](https://github.com/DhairyaLGandhi/), [Elliot Saba](https://github.com/staticfloat).

### Multi-GPU training

Implement and demonstrate multi-GPU parallelism. One route is to expose communication primitives from NVIDIA's [NCCL](https://developer.nvidia.com/nccl) library and use these to build tooling for model parallelism and distributed training. The project should demonstrate parallel training of a Flux model with benchmarks.

Mentors: [Valentin Churavy](https://github.com/vchuravy), [Tim Besard](https://github.com/maleadt)

### Distributed Training

Add a distributed training API to Flux, possibly inspired by PyTorch's equivalent. Any distributed training algorithm could be used (ideally the foundations make it easy to experiment with different setups), though the easiest is likely to implement an MXNet-like parameter server. It should demonstrate training a Flux model with data distributed over multiple nodes, with benchmarks.

Mentors: [Valentin Churavy](https://github.com/vchuravy), [Tim Besard](https://github.com/maleadt)

### Sparse GPU and ML support

While Julia supports dense GPU arrays well via [CUDA.jl](https://github.com/JuliaGPU/CUDA.jl), we lack up-to-date wrappers for sparse operations. This project would involve wrapping CUDA's sparse support, with [CUSPARSE.jl](https://github.com/JuliaGPU/CUSPARSE.jl) as a starting point, adding them to CUDA.jl, and perhaps demonstrating their use via a sparse machine learning model.

### NLP Tools and Models

Build deep learning models for Natural Language Processing in Julia. [TextAnalysis](https://github.com/juliatext/TextAnalysis.jl)  and [WordTokenizers](https://github.com/JuliaText/WordTokenizers.jl) contains the basic algorithms and data structures to work with textual data in Julia. On top of that base, we want to build modern deep learning models based on recent research. The following tasks can span multiple students and projects.

It is important to note that we want practical, usable solutions to be created, not just research models. This implies that a large part of the effort will need to be in finding and using training data, and testing the models over a wide variety of domains. Pre-trained models must be available to users, who should be able to start using these without supplying their own training data.

* Implement [ELMo](https://allennlp.org/elmo) in Julia
* Implement [ALBERT](https://ai.googleblog.com/2019/12/albert-lite-bert-for-self-supervised.html) in Julia
* Implement GPT/GPT-2 in Julia
* Implement [extractive summarisation based on Transformers](https://arxiv.org/abs/1909.03186)
* Implement practical models for
  * Dependency Tree Parsing
  * Morphological extractions
  * Translations (using Transformers)
* Indic language support -- validate and test all models for Indic languages
  * ULMFiT models for Indic languages
* Chinese tokenisation and parsing

**Mentors**: [Avik Sengupta](https://github.com/aviks/)

### Automated music generation

Neural network based models can be used for music analysis and music generation (composition). A suite
of tools in Julia to enable research in this area would be useful. This is a large, complex project that
is suited for someone with an interest in music and machine learning. This project will need a mechanism
to read music files (primarily MIDI), a way to synthesise sounds, and finally a model to learn composition.
All of this is admittedly a lot of work, so the exact boundaries of the project can be flexible, but this can be an
exciting project if you are interested in both music and machine learning.

**Recommended Skills**: Music notation, some basic music theory, MIDI format, Transformer and LSTM architectures

**Resources**: [Music Transformer](https://magenta.tensorflow.org/music-transformer), [Wave2MIDI2Wave](https://magenta.tensorflow.org/maestro-wave2midi2wave)

**Mentors**: [Avik Sengupta](https://github.com/aviks/)

### Neural networks for solving differential equations

Neural networks can be used as a method for efficiently solving difficult partial
differential equations. Efficient implementations from recent papers are being
explored as part of the [NeuralNetDiffEq.jl](https://github.com/JuliaDiffEq/NeuralNetDiffEq.jl)
package. The [issue tracker](https://github.com/JuliaDiffEq/NeuralNetDiffEq.jl/issues)
contains links to papers which would be interesting new neural network based methods to
implement and benchmark against classical techniques.

**Recommended Skills**: Background knowledge in numerical analysis and machine learning.

**Expected Results**: New neural network based solver methods.

**Mentors**: [Chris Rackauckas](https://github.com/ChrisRackauckas)

### Accelerating optimization via machine learning with surrogate models

In many cases, when attempting to optimize a function `f(p)` each calculation
of `f` is very expensive. For example, evaluating `f` may require solving a
PDE or other applications of complex linear algebra. Thus, instead of always
directly evaluating `f`, one can develop a surrogate model `g` which is
approximately `f` by training on previous data collected from `f` evaluations.
This technique of using a trained surrogate in place of the real function
is called surrogate optimization and mixes techniques from machine learning
to accelerate optimization.

Advanced techniques [utilize radial basis functions](https://www.cambridge.org/core/journals/acta-numerica/article/kernel-techniques-from-machine-learning-to-meshless-methods/00686923110F799A1537C4F02BBAAE8E) and Gaussian
processes in order to interpolate to new parameters to estimate `f` in areas
which have not been sampled. [Adaptive training techniques](http://www.ressources-actuarielles.net/EXT/ISFA/1226.nsf/9c8e3fd4d8874d60c1257052003eced6/e7dc33e4da12c5a9c12576d8002e442b/$FILE/Jones01.pdf) explore how to pick new areas
to evaluate `f` to better hone in on global optima. The purpose of this project
is to explore these techniques and build a package which performs surrogate
optimizations.

**Recommended Skills**: Background knowledge of standard machine learning,
statistical, or optimization techniques. Strong knowledge of numerical analysis
is helpful but not required.

**Expected Results**: Library functions for performing surrogate optimization
with tests on differential equation models.

**Mentors**: [Chris Rackauckas](https://github.com/ChrisRackauckas)

### Parameter estimation for nonlinear dynamical models

Machine learning has become a popular tool for understanding data, but scientists
typically understand the world through the lens of physical laws and their
resulting dynamical models. These models are generally differential equations
given by physical first principles, where the constants in the equations such
as chemical reaction rates and planetary masses determine the overall dynamics.
The inverse problem to simulation, known as parameter estimation, is the process
of utilizing data to determine these model parameters.

The purpose of this project is to utilize the growing array of statistical,
optimization, and machine learning tools in the Julia ecosystem to build
library functions that make it easy for scientists to perform this parameter
estimation with the most high-powered and robust methodologies. Possible projects
include improving methods for Bayesian estimation of parameters via Stan.jl
and Julia-based libraries like Turing.jl, or global optimization-based approaches.
Novel techniques like classifying model outcomes via support vector machines
and deep neural networks is can also be considered. Research and benchmarking
to attempt to find the most robust methods will take place in this project.
Additionally, the implementation of methods for estimating structure, such
as [topological sensitivity analysis](http://www.pnas.org/content/111/52/18507)
along with performance enhancements to existing methods will be considered.

Some work in this area can be found in
[DiffEqParamEstim.jl](https://github.com/JuliaDiffEq/DiffEqParamEstim.jl)
and [DiffEqBayes.jl](https://github.com/JuliaDiffEq/DiffEqBayes.jl). Examples
can be found [in the DifferentialEquations.jl documentation](http://docs.juliadiffeq.org/latest/analysis/parameter_estimation.html).

**Recommended Skills**: Background knowledge of standard machine learning,
statistical, or optimization techniques. It's recommended but not required that
one has basic knowledge of differential equations and DifferentialEquations.jl.
Using the differential equation solver to get outputs from parameters can
be learned on the job, but you should already be familiar (but not necessarily
an expert) with the estimation techniques you are looking to employ.

**Expected Results**: Library functions for performing parameter estimation
and inferring properties of differential equation solutions from parameters.
Notebooks containing benchmarks determining the effectiveness of various methods
and classifying when specific approaches are appropriate will be developed
simultaneously.

**Mentors**: [Chris Rackauckas](https://github.com/ChrisRackauckas), [Vaibhav Dixit](https://github.com/Vaibhavdixit02)

## Integration of FEniCS.jl with dolfin-adjoint + Zygote.jl for Scientific Machine Learning

Scientific machine learning requires mixing scientific computing libraries with machine learning.
[This blog post highlights how the tooling of Julia is fairly advanced in this field](https://www.stochasticlifestyle.com/the-essential-tools-of-scientific-machine-learning-scientific-ml/) compared to alternatives such as Python,
but one area that has not been completely worked out is integration of automatic differentiation
with partial differential equations.
[FEniCS.jl](https://github.com/JuliaDiffEq/FEniCS.jl) is a wrapper to the
[FEniCS](https://fenicsproject.org/) project for finite element solutions of partial differential
equations. We would like to augment the Julia wrappers to allow for integration with Julia's
automatic differentiation libraries like [Zygote.jl](https://github.com/FluxML/Zygote.jl) by
using [dolfin-adjoint](http://www.dolfin-adjoint.org/en/release/). This would require setting up
this library for automatic installation for Julia users and writing adjoint passes which utilize
this adjoint builder library. It would result in the first total integration between PDEs and
neural networks.

**Recommended Skills**: A basic background in differential equations and Python. Having previous
Julia knowledge is preferred but not strictly required.

**Expected Results**: Efficient and high-quality implementations of adjoints for Zygote.jl over FEniCS.jl functions.

**Mentors**: [Chris Rackauckas](https://github.com/ChrisRackauckas)
