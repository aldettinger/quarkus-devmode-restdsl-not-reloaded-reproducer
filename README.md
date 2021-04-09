# Quarkus Dev Mode Restdsl Not Reloaded Reproducer

Reproduce an issue where a rest dsl xml files does not trigger a reload in dev mode.

# How to reproduce
mvn quarkus:dev
http :8080/steps (output STEP 1 => ok)
in rests.xml, change "STEP 1" to "STEP 2" and save
http :8080/steps (output STEP 1 => ko)

Sometimes, no change is detected.
Sometimes, it displays "Files changed but restart not needed - notified extensions".

While any change in application.properties make the application reloaded which is great.