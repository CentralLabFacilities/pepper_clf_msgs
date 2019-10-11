cmake_minimum_required(VERSION 2.8.3)
project(pepper_clf_msgs)

## Find catkin macros and libraries
## if COMPONENTS list like find_package(catkin REQUIRED COMPONENTS xyz)
## is used, also find other catkin packages
find_package(catkin REQUIRED COMPONENTS actionlib_msgs std_msgs sensor_msgs geometry_msgs message_generation)

###################################
##            MSGS               ##
###################################

add_message_files(
  DIRECTORY msg
  FILES StringArray.msg
        ChoiceGroup.msg
        Choice.msg
        DisplayChoice.msg
)

add_action_files(
  DIRECTORY action
  FILES ToggleComponent.action
        FollowPerson.action
        Animation.action
)

add_service_files(
  DIRECTORY srv
  FILES MLGrasping.srv
        SynchronizedSSL.srv
        BottomCamHDImage.srv
        SetTTSLanguage.srv
	    DepthAndColorImage.srv
	    ColorImage.srv
	    SetImageStreaming.srv
        TranslateString.srv
        MLSpeechRec.srv
        NLP.srv
        SoundPlay.srv
)

generate_messages(
  DEPENDENCIES actionlib_msgs
               std_msgs
		       sensor_msgs
		       geometry_msgs
)


###################################
## catkin specific configuration ##
###################################
catkin_package(CATKIN_DEPENDS actionlib_msgs sensor_msgs geometry_msgs)
