# Ephemeris
Ephemeris Integrator for Solar System

<del> This project is currently under development. The source files are not very user-friendly. </del>

Now this program is very user-friendly. Just run the released executable, and then follow the instructions to perform Ephemeris Integration!

( However for now it has no built-in functions to read/use/interpolate the output ephemeris data. These will be implemented in future. )

For details about physics, see https://www.kamine.cloud/archives/70 and successive articles.

I also rendered an animation of the Moon viewed from the Earth using the results of this program (v0.1.3) and posted it on Bilibili([BV1zb411Z7B4](https://www.bilibili.com/video/BV1zb411Z7B4/))! The animation covered the period of J2000~2040 TDB, including Lunar Phase and Libration, Solar and Lunar Eclipses, and Exact Times of Lunar Phases, Solar Terms, and Zodiac Signs.

- Ephemeris: CPU and GPU Implementation of a Runge-Kutta 12-order integrator for ephemeris integration.

- SolarSystem: Parameters and initial values of Solar Sytem Celestial Bodies at J2000.0 (JD 2451545.0) TDB.

  Including the Sun, 8 major planets (with 77 moons), 5 minor planets (with 8 moons),
343 main-belt asteriods(1 is also minor planet), 31 trans-Neptunians(4 is also minor planets), and 36 point-masses representing the Kuiper-belt.

  Fitted to NASA/JPL Ephemerides.

## Future goal

- **[Done!]** Data Format: <del> For now the output ephemeris are huge and not-space-efficient, 20 years of data can take up to 10GiB. For the ultimate goal of the Great Solar System Ephemerides covering BC 18000 ~ AD 22000, this means 20TiB of storage. </del>
  
  A good compression/approximation/interpolation method (<del> may be </del> lossy) is <del> needed. </del> **implemented!**

- **[Done!]** Data Interpolation: <del> For now the output data is just a sequence of state vectors of all bodies at a constant time cadence. </del> An algorithm is <del> needed </del> **implemented** to interpolate these states to any time point in the range of ephemeris.

- Second-Stage Integration of Small Body Ephemeris: The program should have ability to use the pre-integrated Solar System Ephemeris to further integrate the trajectory of any given small bodies, like asteriods/commets/minor moons/satellites, and create their ephemerides. The test masses may be given by their initial state vectors at any epoch. This should be relatively efficient. A self-adaptive time step integrator is needed.

  Also, to make it possible to refine the ephemeris of pre-integrated bodies with better observational data, physical parameters, or system configuration, without bothering re-integrate the whole Ephemerides, program should provide functionality to exclude the specific pre-integrated bodies when doing second-stage integration, as these are re-introduced as tiny bodies.

- Accessible functionalities to interpolate the generated ephemerides, and create tables of observables/state vectors. These should be implemented as built-in functions that can be invoked by passing command line arguments to the executable.

- ^w^
