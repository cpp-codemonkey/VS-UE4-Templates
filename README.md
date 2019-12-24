# VS-UE4-Templates
A set of C++ item templates for Visual Studio for Unreal Engine to enable creating of new classes from VS instead of the Unreal Editor.

I no longer use the Unreal editor to create classes because it's inconvenient to keep switching back and forth between visual studio and the engine editor. Also, the templates that the engine uses mostly generate empty classes which are not much use. My templates provide you with constructors and the most often used member functions for the relevant class.

One thing I haven't yet worked out how to do is the _API macro. So for a simple actor class like this:
UCLASS()
class CPP_AI_API APatrolPath : public AActor
{
....
};

my template will generate instead:
UCLASS()
class _API APatrolPath : public AActor
{
....
};

You'll have to provide the rest of the macro yourself which is just the name of your game project, in UPPERCASE. Or delete it altogether or you'll get build errors. As to the significance of these macros it's something to do with modules and dlls so it might be best to not delete them.

Also be wary that Visual Studio will try to create your files in the wrong location. When the dialog for a new item appears the location will be set to the intermediate directory. Suppose we have a project called MyProject. Then the location will default (initially) to
MyProject\Intermediate\ProjectFiles. 

Instead, click the "Browse" button and change it to:
MyProject\Source\MyProject.

And, of course, give a more meaningful name other than the default supplied.

See the install.txt file for instructions on how to isntall.
