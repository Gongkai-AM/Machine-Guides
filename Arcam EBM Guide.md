#Arcam EBM guide
This document is meant to introduce users to Arcam EBM manufacturing. This is a living document and work in progress, and is produced under the direction of Gongkai AM.

To get more info on Gongkai or submit user documentation on Arcam or other industrial additive manufacturing machines, contact [Spencer Wright](mailto:s@pencerw.com?subject=Gongkai Guides) or visit [our "How to contribute" guide.](https://github.com/Gongkai-AM/Machine-Guides/blob/master/How%20to%20contribute.md)

Special thanks for this guide goes to [Stavros Tsitsopoulos,](https://www.linkedin.com/in/stavros-tsitsopoulos-a2757114) who created the intial document.

#Introduction
[Arcam AB](http://www.arcam.com/) (Sweden) is a spin-off company from Gothenburg University and was founded in 1997. Arcam is the sole machine manufacturer for EBM technology. The company offers a cost efficient metal powder bed fusion technology for production of high value (often medical and aerospace) components. 

These machines work in a layer-by-layer process much like laser based powder bed fusion machines, but the layer thickness is typically twice the thickness of SLM/DMLS systems.

The technology differs from the rest of powder bed fusion technologies because it utilises an electron beam instead of a laser in order to fuse regions of a powder bed. In order to generate an electron beam, a vacuum is applied to the building chamber and a filament (single crystal metal) is heated up by current (60,000 volts) and an anode cup creates the initial arc.

The electron beam is controlled by a series of magnetic coils that direct, focus and refine the beam. The high kinetic energy of the electrons strikes the powder particles and this action releases thermal energy usually higher than laser (4-5,000 watts). The electron beam can be split into 100 smaller beams allowing for much faster scan speeds and therefore faster build times.

A semi-melted block of powder, or cake, is formed around the part during the build which can be removed and reused. This cake is required to counteract the electrostatic charge build up from the electron beam, but also helps to remove residual stresses within the parts as they are built. The results of an EBM build consist of platform, parts, supports and cake. The cake is blasted away in the powder recovery process after the build and reused, leaving parts, support and platform.

#Cost
The latest offering from Arcam includes the [Q10](http://www.arcam.com/technology/products/arcam-q10/) and [Q20](http://www.arcam.com/technology/products/arcam-q20/) systems. The Q10 has a smaller building volume (200x200x180mm/7.9x7.9x7.1 inches) and is used mainly for medical parts. The Q20 utilises a cylindrical building tank (350mm diameter x 380mm high/ 13.8” diameter x 15” high) and is used for aerospace/automotive components. The cost of a Q10 is around $610,000 US, and the bigger Q20 costs $870,000 US.

The system comes with a lifter mechanism to remove hoppers from the system and a [PRS](http://www.arcam.com/technology/products/powder-handling/) (powder recovery system) but more money will need to be invested for a sieving and mixing unit. Moreover, a chiller unit is needed as well as a steady helium supply (typically bottled).

In the previous systems (the [A2X](http://www.arcam.com/technology/products/arcam-a2x-3/)) preventive maintenance is required for every 400 hours of operation. This involves cleaning f the system from any metallisation that forms inside the chamber, lubricating the moving parts that control the rake mechanism and the bed as well replacing the filament (every build) and glass inner pane. The new systems are more reliable and more production ready. The filament life has been increased to about 500-700 hours of operation, a camera take pictures of every single layer; safety sensors and cooling down blocks are also installed.

Cost of powder material depends on metal alloy composition. A kilogram can cost up to $300 US. Materials include Titanium, Aluminium or cobalt-chrome. 

#Design for EBM
To design optimum parts to be built using additive manufacturing (AM), consideration must be given to the manufacturing process. Every step downstream in the process should be considered during the design stage (even if it is being outsourced to a service bureau) to ensure a suitable outcome. If the build and post processing requirements are not considered at the design stage, redesign and rebuild of the part may be necessary and additional costs will be incurred.

![Figure 1]
(https://github.com/Gongkai-AM/Machine-Guides/blob/master/Figures/Arcam%20Figure%201.png)

The most efficient parts are those specifically designed to be built using AM. The implications of unsuitable designs include:

1. Increased costs due to failed/repeated builds
2. Reduced functionality e.g. rough surfaces or features not to tolerance
3. Wasted resources if builds fail and parts have to be scrapped
4. Time delays caused by unsuccessful builds

AM Design methodology typically follows one of two routes:

##Improving an existing design
Using AM to lightweight, strengthen or add complexity to a component previously manufactured through traditional methods. In many cases, the AM version can be more complex and therefore add value by improving the functionality of the part.

##Solving a new problem
A new part has to be designed to suit its purpose. Different designs and manufacturing processes should be considered to ensure that AM is the most suitable option, and the part’s design should follow the guidelines below so as to take advantage of AM’s strengths.

In both cases the checklist (Figure 1) should help to ensure the design process considers the necessary questions.

![Figure 2]
(https://github.com/Gongkai-AM/Machine-Guides/blob/master/Figures/Arcam%20Figure%202.png)

##Comparison between SLM and EBM

Feature type|SLM|EBM
------------|---|---
Orientation|Upskins/verticals smoother, downskins rougher|Upskins smoother, Vertical/Downskins rougher
Support angle|Bottom edge and surfaces ~45° or less from platform need support|Bottom edge and horizontals or areas vulnerable to over melting & need support
Wall thickness|Minimum 0.3-0.5mm|Minimum 0.6-1.0mm
Details|Small details should be oriented upwards to avoid the need for supports/rougher surface textures
Holes/Tubes|>0.5mm ø vertical; ˂8mm ø horizontal without support|>0.5-2.0mm ø can build but powder removal may be difficult
Machining stock|0.1-0.5mm to be added to machining surfaces|0.5-2.0mm to be added to machining surfaces
Clearance|>0.15mm for assemblies; >1.0mm between parts|>1.0mm between parts removal of powder must be considered
Hollowing|0.3-0.5mm min wall thickness, must add powder release hole|0.6-1.0mm min wall thickness removal of caked powder must be considered
Screw Threads|Should be built vertically, must be tapped/machined|Must be tapped/machined

##EBM DESIGN GUIDES

###Orientation
Arcam recommend that parts in EBM builds should be oriented with as few down facing surfaces as possible, although the support requirements are not quite the same for SLM and EBM. Horizontal surfaces, especially curved ones, are prone to variations in dimensional accuracy and defect formation. 

###Supports
The purpose for supports in EBM differ slightly from SLM due to the consolidated ‘cake’ material that is built around the part. This provides some level of anchoring and thermal conductivity that the loose powder in the SLM process does not. This also reduces thermal stresses inside the part. However, the bottom of the part needs some supports to anchor it to the platform and on some downskins there is a need for additional support material to prevent distortion and maintain dimensional accuracy. Thin overhangs and horizontal edges may result in overheating and distortion. Support structures, similar to those used in SLM and with teeth to enable easy removal, can be added to the part to act as a heat sinks. These can be called ‘wafer supports’. Denser supports are needed on areas of bulk, which require more heat transfer than thin walls. Unlike SLM, these supports do not have to be attached to the platform as the semi-sintered caked powder allows the supports to start building later in the build - allowing for a reduction in wasted material.

###Wall Thickness
It is possible to build vertical walls with a thickness of 0.6mm in solid material, but this can be difficult to achieve in all orientations. A safe all around thickness would be 1mm. For short lengths (e.g. part of a lattice structure), different melt themes can be used so the part can be as thin as 0.3mm. However, this is not suitable for structural walls as they can suffer from delamination or layer shift.

###Details
In general, small surface details should be oriented on upward facing surfaces and free from supports. Very short horizontal bosses or overhangs protruding <1mm can be built without requiring supports, but the lower edges of these will be rough. Longer horizontal protrusions will require supports in EBM - otherwise warping and over melting can occur. As-built surface texture, post processing requirements and access to detailed surfaces for finishing are important to consider. If mechanical finishing or abrasive blasting will be carried out, this may round off fine details or edges.

###Holes
Holes or tubes built into EBM parts at any angle will be filled with semi sintered cake. This block of powder allows different diameters to be built without the need for supports but can be hard to remove unless access to the hole is easily done with blasting media or hand tools, so this must be considered during the design stage. A minimum diameter of 1-2mm vertically or 0.5mm horizontally is recommended to ensure that rough surfaces do not cause the holes to close up.

###Machining Stock
Due to the rougher surfaces produced, 0.5-2.0mm would be a suitable addition for machining stock, depending on the orientation of the surface. More material will need to be removed on rough downskins and verticals than smoother upskins before a dense flat surface is achieved, so this will affect the amount of stock needed in different areas of the part.

###Clearances
As there is a semi sintered cake of powder surrounding the parts that are built, access must be given to allow trapped caked powder to be blasted away from small gaps, holes and mechanisms. Larger spaces may have to be included around complex parts to ensure the cake can be removed. 1mm clearance is assumed to be sufficient to thermally isolate each part on the build platform.

###Hollow parts
Parts built in EBM are embedded in semi sintered cake. This powder is not possible to pour out and must be blasted away. Multiple access holes will be necessary to allow the internal caked powder to be removed by blasting or hand tools. A hollow open lattice form is more suitable for EBM than a more enclosed hollow form due to the constraints of blasting the unmelted powder away from the internal cavity. It is possible to build ‘parts within parts’ using the semi sintered cake as support with EBM. This would be very difficult to support by SLM.

###Screw heads
The surface texture produced by EBM dictates that functional close tolerance screws are not possible to be directly manufactured, but a near net shape version can be built and machined to tolerance afterwards.

###Stacked parts
Multiple components can be stacked on top of one another to maximize the number produced in a single build. They can be attached to the part below with minimal support, and the outer rim has support which is not attached to either the part below or the platform, as it was supported in the semi sintered cake which acts as a thermal conductor to aid heat distribution without the need for full support contact with the platform or the parts below.

#Manufacturing process
Typically, an EBM setup will include the following phases:

1.  **Vacuum down.** Here, the air is evacuated from the building chamber by the use of a pump. This takes about 50-70 minutes. All door seals need to be thoroughly cleaned in order to ensure no leakage is taking place when the door closes. Helium is introduced (0.8 bar pressure).
2.  **Ramp up.** The filament is heated by current. All electron gun components should be free of any metal powder particles in order to avoid arcing. This takes about 10 minutes.
3. **Calibration.** The electron beam spot is adjusted. The process used to be manual, in the new systems is automatic. 5 minutes duration.
4. **Preheating of steel plate.** A temperature of about 750 degrees centigrade needs to be achieved before building starts. This will take about 40-50 minutes. The plate is glowing red and can be seen via the window. Thermocouples will detect the temperature; once it exceeds the preset value, the build will start automatically. When the rake spreads the first layer of powder across, no ‘smoke’ should occurs that will send particles flying around the chamber and reach the electron gun cylinder. Smoke is a term which describes any violent displacement of powder due to the electrically charged electrons. If that happens the system will auto start. If three ‘smoke’ incidents happen in a row, the system automatically shuts down. Smokes can occur during building as well. To avoid any fallout concentration on the part, the rake will move across to make sure excessive powder particles are not on the surface of the bed.
5. **Cooldown.** When the build is finished, the tank inside the building chamber needs to cool for another 12-18 hours, depending on the build height. Heated titanium powder can be potentially explosive if the tank is exposed to ambient air.
6. **Removal.** After the cake has cooled down sufficiently (below 100 degrees) the tank is removed and part is taken out. The unused powder can be sieved and topped up with new powder and used again.

#Post processing
After a build is complete, it is removed from the machine by the operator. Various processes are then necessary before the completed part can be used.

1. **Powder recovery/Blasting:** EBM parts are removed from the machine with a semi sintered block of caked powder around the parts. Arcam provide a Powder Recovery System (PRS), which is recommended for use with their EBM machines. It is a sealed air pressure blasting chamber which enables recovery of unmelted caked powder in a build. The media used in the PRS is the same as the powder used in the build, so media and caked powder can be mixed in the PRS process, sieved, and returned to the machine for the next build without being contaminated. Multiple PRS systems are advised if a variety of powders are to be used, as cleaning may be difficult and therefore cross contamination of metal powders is potentially an issue. 
The time taken to blast unmolten powder from a build can vary according to the complexity of the parts, but 75-80% of the unmolten powder in 5-7mm diameter hollow cylinders of varying lengths can generally be removed in the first 30 seconds of blasting, increasing to 98% after 6 minutes. However, the more corners or blind holes a shape has, the longer powder may take to be removed by blasting and the entire amount may not be possible to remove in this way.
It is likely in complex or angular shapes that using only the PRS will not remove a sufficient amount of powder. Other techniques of powder removal, for example using hand tools to scrape or break the powder cake away, may be sufficient to remove the cake. This will result in powder losses as it is not possible to return powder to the machine after contamination with other tools outside the PRS. An ultrasonic tool can also be an option to remove trapped volumes of powder from internal passageways. A conformal tool to the shape of the orifice can avoid abrasion and therefore minimise any cross contamination.
2. **Support removal:** Fewer supports are required for EBM due to the caked powder surrounding the part, but the supports that are required for additional heat transfer should be possible to remove in the same way as SLM parts. The empty platforms can be reused straight away, if there is a need they can be resurfaced mechanically e.g. by machining, EDM wire cutting or spark erosion.
3. **Heat treatment:** Because there is no residual build-in stresses in the EBM part, post heating is usually not necessary. This is due to the caked powder around EBM parts being held in a vacuum at high temperature in the EBM process, which anneals the material as the layers build up and relieves the stresses in the part as the build progresses. Surfaces that are attached directly to the build platform by supports are stress relieved during the build, but any parts that do not have supports are susceptible to higher stresses. Heat treatment can be used to improve material properties of EBM parts, for example the hardness of EBM built NiTi alloys has been found to decrease with increasing temperature but at critical temperature (660 degrees centigrade) the hardness increases with rising temperature.
4. **Hot Isostatic Pressing (HIP):** HIP is well suited to EBM because the build process takes places in vacuum, therefore any internal pores also contain a vacuum and can be collapsed readily. These will not be susceptible to thermally induced porosity and the material will remain dense.
5. **Machining:** The points to consider when designing are which surfaces of the part need to be machined for accuracy, additional stock considerations and should fixing be added to the part design to allow it to be clamped or secured for easier machining. Furthermore, can rougher as-built surfaces remain in some areas? Moreover, will it be possible to access surfaces to be machined once the part has been built?
6. **Surface Finishing:** The surface finish required on the part can affect the design. Sometimes a standard blasted or shot peened finish is suitable. If further finishing or polishing is required, this can include:
  * **Automatic** – disc finishing, drag finishing, stream finishing, vibratory finishing, barrel finishing, pulse finishing, electropolishing, laser polishing
  * **Manual** – hand polishing, using polishing mops, wheels, hand held tools.


<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/80x15.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.
