

## Associated (Child) Resources

When a primary resource defines the key 'resources' with a list of additional resources these are the child resources.
The child resource's reference to the parent will be automatically added to the rendered template

when rendering the associated resource:
1. the parent (primary) resource is known
2. the child resource can reference the parent’s type as primary_artifact.metadata.type
3. the child looks up that type in its associated hash associated[primary_artifact.metadata.type] the value of which is the attribute name it uses
4. the child’s attribute value is ${primary_artifact.metadata.type.primary_artifact.metadata.name.id}
