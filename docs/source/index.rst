.. abTEM documentation master file, created by
   sphinx-quickstart on Fri Dec 27 18:19:25 2019.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

abTEM: ab initio Transmission Electron Microscopy
====================================================
**This document is under construction. Please be aware and report issues.**

abTEM provides a Python API for running simulations of Transmission Electron Microscopy images. It is written entirely
in Python, which enables easy integration with first-principles codes and analysis tools accessible from Python,
and allows for a simple and intuitive user interface. The computationally demanding parts are implemented using
jit-compiled Numba code and high-performance libraries, maintaining speed while ensuring portability.

abTEM works with the Atomic Simulation Environment and the density functional theory code GPAW to provide an seamless
environment for simulating images from first principles.

>>> from ase.io import read
>>> from abtem.waves import PlaneWave
>>> atoms = read('SrTiO.cif')
>>> plane_wave = PlaneWave(sampling=0.01, energy=300e3)
>>> exit_wave = plane_wave.multislice(atoms)
>>> image_wave = exit_wave.apply_ctf(defocus=200, focal_spread=40)
>>> image_wave.show()

.. toctree::
   :maxdepth: 1

   install
   walkthrough/introduction
   modules/api
   about
