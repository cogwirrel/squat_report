squat_report
============

Report for individual project - squat


Plan:

Title

Abstract
	Intro to powerlifting/lifting in general
	Problem of squat form
	Solution achieved
	Conclusions

Acknowledgements
	Ajd - lots of help with design decisions/overall algorithm/planning
	Duncan Gillies - ????
	Tom Wilding - foot pinning
	Greg Pye - fellow lifter - verbal feedback idea

Contents

Intro
	Powerlifting
	The Problem
	Approach

Background
	Comprehensive Existing solutions? Barsense - bar velocity for olympic lifts
	Push - force/rep tracking using hardware/motion sensor
	Video Approach - stereo
	Foreground Segmentation
	Models

Main Report Body
	Squats
		Difficult technique, easy to get injured etc.
		Technical squat specification

	Core algorithm
		Detection Stage
			Background subtraction mog with high learning rate to ensure surroundings/camera still
			User indicates start - walks into view and detected using background subtraction and motion detection (waits until figure is present and still)
			Model initialisation to height of figure.
			Toes pinned
		Squatting Stage
			Background Subtraction
				Naive subtraction
				Naive subtraction with shadow removal
				Largest Object
			Model
				Blob model (ovals)
				Degrees of freedom are angles
			Optimisation/Fitting
				Optimisation algorithm - bobyqa - apache commons
				Cost/fit function
					'Draw' the model
					Maximise overlap
			Squat Analysis
				Check angle conditions after fit on each frame
				Track position of hip over time to detect upward/downward movement
				Events triggered under certain conditions for high level view
				Squat Rep Counting and Scoring
		Finishing Stage
			Detect when feet out of position (walk away to finish)
	Implementation
		Linux, then port to android
		Cool code stuff eg. listeners
		Optimisation - matmanager!
		Libraries - OpenCV, apache commons
	Application Overview/Features
		UI
		Real time feedback - beep and voice
		Score breakdown
		Settings/Preferences
			Different environments/situations
			Performance/Accuracy trade-off

Evaluation
	Technical benchmarks?
	Useability, practicality and general performance

Future Work
	Recording for later viewing
	More lifts - deads, bench, clean & jerk, snatch
	Application in other areas - sports eg. cycling/gymnastics, interactive ui/game
	Stereo camera phone
	Plan to release on app store + popularity on reddit etc.

Conclusion
	It's awesome

References

Appendix