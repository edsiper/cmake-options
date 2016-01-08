project(project-A C)

option(WITH_FEATURE_AA  "Enable Feature AA"   ON)
option(WITH_FEATURE_BB  "Enable Feature BB"   OFF)

message(STATUS ">>>>>>>> Project_A: Feature AA: " ${WITH_FEATURE_AA} " <<<<<<<<")
message(STATUS ">>>>>>>> Project_A: Feature BB: " ${WITH_FEATURE_BB} " <<<<<<<<")
