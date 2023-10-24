source 'https://cdn.cocoapods.org'

$minVersion = '14.1'

platform :ios, $minVersion

def shared_pods
  pod 'MapboxDirections.swift', :git => 'https://github.com/flitsmeister/Mapbox-directions-swift', :tag => 'v0.23.1'
  pod 'Turf', :git => 'https://github.com/flitsmeister/turf-swift', :tag => 'v0.2.2'
  pod 'Polyline', '~> 4.2'
  pod 'Nimble', '12.3.0'
  pod 'Quick', '6.1.0'
  pod 'iOSSnapshotTestCase', '8.0.0'
end

target 'MapboxNavigation' do
  use_frameworks!

  shared_pods
  pod 'Solar', :git => 'https://github.com/ceeK/Solar', :tag => '3.0.1'
  pod 'MapboxGeocoder.swift', '0.15.0'
  pod 'MapboxSpeech', '2.1.1'
end

target 'MapboxCoreNavigation' do
  use_frameworks!

  shared_pods
end

post_install do |installer|
  installer.pods_project.targets.each do |target|
    target.build_configurations.each do |config|
      config.build_settings['IPHONEOS_DEPLOYMENT_TARGET'] = $minVersion
    end
  end
end
