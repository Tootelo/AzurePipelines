# Notes de version    

**Application** : {{releaseDetails.releaseDefinition.name}} <br/>
**Version** : $(Version)#{{buildDetails.id}} <br/>
**Numéro de livraison**  : {{releaseDetails.name}} <br/>
**Date** : {{date releaseDetails.modifiedOn "YYYY-MM-DD"}} <br/> 


{{#group workItems by="fields['Custom.Type']"}}


{{#forEach items}}

{{#eq (lookup this.fields 'System.WorkItemType') "User Story"}}

{{#if isFirst}}
# Catégorie : {{lookup this.fields 'Custom.Type'}}
{{/if}}
*  **{{this.id}}** - **{{lookup this.fields 'System.Tags'}}**
{{#if (lookup this.fields 'Custom.Notesdeversion')}}
{{{lookup this.fields 'Custom.Notesdeversion'}}}
{{else}}
{{lookup this.fields 'System.Title'}}
{{/if}}


{{/eq}}

{{/forEach}}


{{/group}}






