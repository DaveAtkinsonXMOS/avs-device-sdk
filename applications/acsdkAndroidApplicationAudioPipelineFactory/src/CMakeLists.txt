cmake_minimum_required(VERSION 3.1 FATAL_ERROR)

add_definitions("-DACSDK_LOG_MODULE=acsdkAndroidApplicationAudioPipelineFactory")

add_library(acsdkAndroidApplicationAudioPipelineFactory SHARED
        AndroidApplicationAudioPipelineFactory.cpp)

target_include_directories(acsdkAndroidApplicationAudioPipelineFactory PUBLIC
        ${acsdkAndroidApplicationAudioPipelineFactory_SOURCE_DIR}/include)

target_link_libraries(acsdkAndroidApplicationAudioPipelineFactory
        acsdkApplicationAudioPipelineFactoryInterfaces
        acsdkEqualizerInterfaces
        acsdkShutdownManagerInterfaces
        AVSCommon
        AndroidSLESMediaPlayer
        AndroidUtilities
        Captions
        )

# install target
asdk_install()
